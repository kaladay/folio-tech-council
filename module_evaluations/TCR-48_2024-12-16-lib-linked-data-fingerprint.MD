# Module acceptance criteria template

## Module Name
lib-linked-data-fingerprint

## How to use this form
When performing a technical evaluation of a module, create a copy of this document and use the conventions below to indicate the status of each criterion.  The evaluation results should be placed in the [module_evaluations](https://github.com/folio-org/tech-council/tree/master/module_evaluations) directory and should conform to the following naming convention: `{JIRA Key}_YYYY-MM-DD-{module name}.MD`, e.g. `TCR-1_2021-11-17-mod-foo.MD`.  The date here is used to differentiate between initial and potential re-evaluation(s).  It should be the date when the evaluation results file was created.

* [x] ACCEPTABLE
* [x] ~INAPPLICABLE~
* [ ] UNACCEPTABLE
  * comments on what was evaluated/not evaluated, why a criterion failed

## [Criteria](https://github.com/folio-org/tech-council/blob/7b10294a5c1c10c7e1a7c5b9f99f04bf07630f06/MODULE_ACCEPTANCE_CRITERIA.MD)

## Administrative
* [ ] Listed by the Product Council on [Functionality Evaluated by the PC](https://wiki.folio.org/display/PC/Functionality+Evaluated+by+the+PC) with a positive evaluation result.

## Shared/Common
* [x] Uses Apache 2.0 license
* [x] INAPPLICABLE (library) Module build MUST produce a valid module descriptor
* [x] INAPPLICABLE (library) Module descriptor MUST include interface requirements for all consumed APIs
* [x] Third party dependencies use an Apache 2.0 compatible license
* [x] Installation documentation is included
  * -_note: read more at https://github.com/folio-org/mod-search/blob/master/README.md_
* [x] INAPPLICABLE (library) Personal data form is completed, accurate, and provided as `PERSONAL_DATA_DISCLOSURE.md` file
* [x] Sensitive and environment-specific information is not checked into git repository
* [x] Module is written in a language and framework from the [officially supported technologies](https://wiki.folio.org/display/TC/Officially+Supported+Technologies) page[^1]
* [x] Module only uses FOLIO interfaces already provided by previously accepted modules _e.g. a UI module cannot be accepted that relies on an interface only provided by a back end module that hasn't been accepted yet_
* [x] Module gracefully handles the absence of third party systems or related configuration
* [x] Sonarqube hasn't identified any security issues, major code smells or excessive (>3%) duplication (6); and any disabled or intentionally ignored rules/recommendations are reasonably justified.
  * See [Rule Customization](https://dev.folio.org/guides/code-analysis/#rule-customization) details. 
* [x] Uses [officially supported](https://wiki.folio.org/display/TC/Officially+Supported+Technologies) build tools[^1]
* [x] Unit tests have 80% coverage or greater, and are based on [officially supported technologies](https://wiki.folio.org/display/TC/Officially+Supported+Technologies)[^1]



## Backend
* [x] INAPPLICABLE (library): Module's repository includes a compliant Module Descriptor
  * -_note: read more at https://github.com/folio-org/okapi/blob/master/okapi-core/src/main/raml/ModuleDescriptor.json_
* [x] INAPPLICABLE (library): Module includes executable implementations of all endpoints in the provides section of the Module Descriptor
* [x] INAPPLICABLE (library): Environment vars are documented in the ModuleDescriptor
  * -_note: read more at [DR-000020 - Teams must document deployment requirements in a clear & consistent way](https://folio-org.atlassian.net/wiki/spaces/TC/pages/5055298/DR-000020+-+Teams+must+document+deployment+requirements+in+a+clear+consistent+way)_
* [x] INAPPLICABLE (library): If a module provides interfaces intended to be consumed by other FOLIO Modules, they must be defined in the Module Descriptor "provides" section, and must conform to FOLIO [interface naming conventions](https://dev.folio.org/guidelines/naming-conventions/#interfaces).
* [x] INAPPLICABLE (library): All API endpoints are documented in OpenAPI.
* [x] INAPPLICABLE (library): All API endpoints protected with appropriate permissions as per the following guidelines and recommendations, e.g. avoid using `*.all` permissions, all necessary module permissions are assigned, etc.
  * -_note: read more at https://dev.folio.org/guidelines/naming-conventions/ and https://wiki.folio.org/display/DD/Permission+Set+Guidelines_
* [x] INAPPLICABLE (library): Module provides reference data (if applicable), e.g. if there is a controlled vocabulary where the module requires at least one value
* [x] INAPPLICABLE (library): If provided, integration (API) tests must be written in an [officially supported technology](https://wiki.folio.org/display/TC/Officially+Supported+Technologies)[^1]
  * -_note: while it's strongly recommended that modules implement integration tests, it's not a requirement_
  * -_note: these tests are defined in https://github.com/folio-org/folio-integration-tests_
* [x] INAPPLICABLE (library): Data is segregated by tenant at the storage layer
* [x] INAPPLICABLE (library): The module doesn't access data in DB schemas other than its own and public
* [x] Any dependencies, other than on defined interfaces, are declared in the README.md.
* [x] INAPPLICABLE (library):The module responds with a tenant's content based on x-okapi-tenant header
* [x] INAPPLICABLE (library): Standard GET `/admin/health` endpoint returning a 200 response
  * -_note: read more at https://wiki.folio.org/display/DD/Back+End+Module+Health+Check+Protocol_
* [x] High Availability (HA) compliant
  * Possible red flags:
    * Connection affinity / sticky sessions / etc. are used
    * Local container storage is used
    * Services are stateful
* [x] Module only uses infrastructure / platform technologies on the [officially supported technologies](https://wiki.folio.org/display/TC/Officially+Supported+Technologies) list.[^1]
  * _e.g. PostgreSQL, ElasticSearch, etc._

## TCR Process Improvements
[_Please include here any suggestions that you feel might improve the TCR Processes._]

[^1]: Refer to the [Officially Supported Technologies](https://wiki.folio.org/display/TC/Officially+Supported+Technologies) page for the most recent ACTIVE release.
