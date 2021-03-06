# SC4-1-1-idref

## Description
This test checks that each element referred to from an idref attribute exists.


## Background
- [F17: Failure of Success Criterion 1.3.1 and 4.1.1 due to insufficient information in DOM to determine one-to-one relationships (e.g., between labels with same id) in HTML](http://www.w3.org/TR/2014/NOTE-WCAG20-TECHS-20140311/F17)
- [eGovMon test ID: F17-2](http://wiki.egovmon.no/wiki/SC4.1.1#Element_with_.40for)


## Assumptions
*no known assumptions*


## Test properties
| Property          | Value
|-------------------|----
| Test name         | Reference elements
| Test requirement  | 4.1.1 Parsing
| Test mode         | Automatic
| Test environment  | DOM
| Test subject      | Single web page


## Test procedure

### Selector
Test method: [automatic][earl:automatic]

Select each label element with a for attribute and each element with a aria-activedescendant attribute. The CSS selector "label[for], *[aria-activedescendant]" can be used.

### Step 1
Test method: [automatic][earl:automatic]

- Take the attribute with the IDREF (for=""/aria-activedescendant) value as IdrefAttr
- Trim the IdrefAttr of whitespace characters
- Select element IdTarget, by looking up the first element that has an ID attribute that matches the IdrefAttr
- IF idTarget exists:
  - Return SC4-1-1-idref-pass1
- ELSE:
  - Return SC4-1-1-idref-fail1


| Outcome  | Passed
|----------|-----
| Testcase | SC4-1-1-idref
| Pointer  | selector result
| ID       | SC4-1-1-idref-pass1

| Outcome  | Failed
|----------|-----
| Testcase | SC4-1-1-idref
| Error    | The attribute {IdrefAttr} refers to an element that does not exist on the page.
| Pointer  | selector result
| ID       | SC4-1-1-idref-fail1



[earl:automatic]: ../earl/automatic.md
[earl:semiauto]: ../earl/semiauto.md
[earl:manual]: ../earl/manual.md