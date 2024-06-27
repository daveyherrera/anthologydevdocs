---
title: Tips for using the Get and Save API operations
id: get-save-bestpractices
sidebar_position: 2
author: Jim Burns
published: '2024-04-23'
edited: '2024-04-23'
---

<VersioningTracker frontMatter={frontMatter}/>

A large subset of the available APIs in Anthology Student have a scope of inserting and updating single instances of an entity. Every entity in the Student data model inherits from a base entity service. The available operations in the base entity service are Get, Create, SaveNew, Save and Delete. There are some entities in the model that have additional APIs implemented for inserting and updating data. These will be reflected with additional endpoints that are documented in Swagger. The focus of this document will outline best practices for how to update an existing instance of an entity utilizing the Get and Save endpoints.

## Swagger documentation

The use case that will be used as an example in this document will be to update an existing record in the Student entity. The list of available API endpoints that can be used for the Student entity are shown below. Using the Get and Save endpoints will be covered in this document.

![Operations for Student entity](/assets/img/StudentAPI_Get_Save_Operations1.png)
![Operations for Student entity](/assets/img/StudentAPI_Get_Save_Operations2.png)

## Get Operation

The first step will be to execute this operation for the entity you are updating an existing record record for. The request for this operation is the Id value of the entity row you want to update. The response from this operation will be the fully populated entity. The request payload for ALL Save endpoints is the entity itself. The execution logic of the Save endpoints in most cases align with a PUT verb in REST as opposed to a PATCH. Thus, you want to make sure that the entity is fully populated with existing data in order to prevent any data being unintentionally overwritten when the Save operation is executed.
Below is the response received when executing the Get endpoint. Copy/Paste the section of the response below that is inside the “data” element. This will be your starting payload for the Save endpoint.

```
{
"payload": {
"data": {
"isExcludedCrmIntegration": false,
"addressTypeId": 0,
"studentInquiryRequired": true,
"extraCurricularsList": [],
"programsList": [
10
],
"enrolledProgramIdList": [],
"ethnicitiesList": [
6
],
"leadSourcesList": [
691
],
"deleteVeteranDetails": false,
"vendors": [],
"studentAddressAssociation": 0,
"newAssignedAdmissionsRepId": 0,
"assignedAdmissionsRepReassignedDate": "0001/01/01 00:00:00",
"studentRelationshipAddress": null,
"lastFourSsn": "9023",
"customProperties": {},
"multiValueCustomProperties": {},
"originalCustomPropertiesValues": null,
"originalMultiValueCustomPropertiesValues": null,
"genderPronounList": [],
"overridePrevEducAltPellValidation": false,
"id": 50508,
"acgEligReasonCode": null,
"agencyId": 0,
"alienNumber": "",
"arAccountStatus": "X",
"arBalance": 217039.25,
"arNextTransactionNumber": 47,
"assignedAdmissionsRepId": 66,
"athleticIdentifier": null,
"bestTimeToContact": "Anytime",
"campusId": 5,
"citizenId": 2,
"city": "Appleburg ",
"collegeId": null,
"countryId": 1,
"countyId": 0,
"createdDateTime": "2022/08/10 12:46:03",
"cumulativeGpa": 4,
"cumulativeGpaPoints": 12,
"currencyCodeId": null,
"currentLda": "2024/01/12 00:00:00",
"dataBlockIndicator": false,
"dateOfBirth": "1990/03/10 00:00:00",
"dbiModifiedDate": null,
"defaultAddressCode": null,
"defaultMasterStudentAddressId": null,
"defaultStudentAddressId": null,
"disabled": "",
"driverLicenseNumber": "",
"driverLicenseState": "",
"emailAddress": "chase@pathify.com",
"employabilityAboutInfo": null,
"employerId": 0,
"employmentStatusId": 0,
"externalStudentIdentifier": null,
"extraCurricularActivityId": 0,
"facebookUrl": null,
"faGradPlusCounselingDate": null,
"faRigorousHighSchoolProgramCodeId": null,
"firstName": "Chase",
"genderId": 6,
"gpaCredits": 3,
"hispanicLatino": "N",
"hsAcademicGpa": null,
"instagramUrl": null,
"isActive": true,
"isAllowedBulkRegistrationByTrack": null,
"isBadAddress": false,
"isBadPhone": false,
"isClearinghouseDataBlockIndicator": false,
"isDdVeteran": false,
"isEftDefaultForStipends": false,
"isInDistrict": false,
"isSscrError11Received": false,
"lastActivityDate": null,
"lastInterestDate": null,
"lastModifiedDateTime": "2024/04/03 06:56:56",
"lastModifiedUserId": 3186,
"lastName": "Williams",
"lastNameFirstFour": "Will",
"lastStatementBeginDate": null,
"lastStatementCloseDate": null,
"lastStatementDate": null,
"leadDate": "2022/08/10 12:46:00",
"leadSourceId": 691,
"leadTypeId": 3,
"linkedInUrl": null,
"maidenName": "",
"maritalStatusId": 1,
"mi": "E",
"middleName": "Eratosthenes",
"mobilePhoneNumber": " ",
"nationalityId": 15,
"nickName": "",
"niStudent": false,
"note": " ",
"originalAssignedAdmissionsRepId": 66,
"originalExpectedStartDate": null,
"originalStartDate": "2023/08/29 13:44:30",
"otherEmailAddress": "",
"otherLanguageFirstName": null,
"otherLanguageLastName": null,
"otherLanguageMiddleName": null,
"otherLanguageStudentFullName": null,
"otherPhoneNumber": "",
"personId": 853,
"phoneNumber": "(112) 323-4345",
"pin": 9023,
"postalCode": "75053",
"postalCodeFirstThree": "750",
"preferredContactType": "Ph",
"preferredName": null,
"previousEducationGpa": null,
"previousEducationId": 7,
"programGroupId": 6,
"programId": 10,
"rawFirstName": "Chase",
"rawLastName": "Williams",
"rawPhoneNumber": "1123234345",
"rowVersion": "AAAAAAMotC4=",
"schoolStatusId": 14,
"shiftId": 2,
"smsServiceProviderId": null,
"sourceSystem": "C",
"ssn": "343-27-9023",
"startDate": "2022/08/22 00:00:00",
"state": "TX",
"statementComment": " ",
"streetAddress": "46 Applewood Street",
"streetAddress2": null,
"studentFullName": null,
"studentIdentifier": null,
"studentNumber": "749",
"subscribeToSms": false,
"suffix": null,
"suffixId": null,
"titleId": 1,
"twitterUrl": null,
"veteran": "",
"workPhoneNumber": "",
"workPhoneNumberExtension": "",
"originalState": "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",
"secureState": "H4sIAAAAAAAEAD3MQQrCMBAAwK9I7mZTeysqeFbpoSJel5C0C01Ssisxvl6s4ANm9qecsfb+7Ood56frPUumOGKst7q4zSvMkQ9qElk6ALaTC8g6kM2JkxdtU4CdMS00BgaXCWd6o1CKsMasfkNH/6OUokurUx6/sIHH9TKs7ZYiC0brFBw/juQnSpcAAAA=",
"extendedProperties": [],
"entityState": 3
},
"count": 1
},
"notifications": [],
"hasError": false,
"hasFault": false,
"hasWarning": false,
"hasValidationError": false,
"hasValidationWarning": false,
"hasValidationInformation": false,
"hasSecurityError": false
}
```

## Save Operation

This is the operation that is used to update an instance of the entity. Using the object returned from the call to the Get endpoint above, update the applicable properties with the desired values. Below is an example of a payload for updating an existing instance of the Student entity. A couple of notes. If you are updating any portion of the address or changing the phone number, make sure the studentAddressAssociation property is set to 2. If this is not done, then a validation error message will be returned in the response. Additionally, the entityState property should be set to 2 indicating that the record is being modified.

```
{
"payload": {
"isExcludedCrmIntegration": false,
"addressTypeId": 0,
"studentInquiryRequired": true,
"extraCurricularsList": [],
"programsList": [
10
],
"enrolledProgramIdList": [],
"ethnicitiesList": [
6
],
"leadSourcesList": [
691
],
"deleteVeteranDetails": false,
"vendors": [],
"studentAddressAssociation": 0,
"newAssignedAdmissionsRepId": 0,
"assignedAdmissionsRepReassignedDate": "0001/01/01 00:00:00",
"studentRelationshipAddress": null,
"lastFourSsn": "9023",
"customProperties": {},
"multiValueCustomProperties": {},
"originalCustomPropertiesValues": null,
"originalMultiValueCustomPropertiesValues": null,
"genderPronounList": [],
"overridePrevEducAltPellValidation": false,
"id": 50508,
"acgEligReasonCode": null,
"agencyId": 0,
"alienNumber": "",
"arAccountStatus": "X",
"arBalance": 217039.25,
"arNextTransactionNumber": 47,
"assignedAdmissionsRepId": 66,
"athleticIdentifier": null,
"bestTimeToContact": "Anytime",
"campusId": 5,
"citizenId": 2,
"city": "Appleburg ",
"collegeId": null,
"countryId": 1,
"countyId": 0,
"createdDateTime": "2022/08/10 12:46:03",
"cumulativeGpa": 4,
"cumulativeGpaPoints": 12,
"currencyCodeId": null,
"currentLda": "2024/01/12 00:00:00",
"dataBlockIndicator": false,
"dateOfBirth": "1990/03/10 00:00:00",
"dbiModifiedDate": null,
"defaultAddressCode": null,
"defaultMasterStudentAddressId": null,
"defaultStudentAddressId": null,
"disabled": "",
"driverLicenseNumber": "",
"driverLicenseState": "",
"emailAddress": "chase@pathify.com",
"employabilityAboutInfo": null,
"employerId": 0,
"employmentStatusId": 0,
"externalStudentIdentifier": null,
"extraCurricularActivityId": 0,
"facebookUrl": null,
"faGradPlusCounselingDate": null,
"faRigorousHighSchoolProgramCodeId": null,
"firstName": "Chase",
"genderId": 6,
"gpaCredits": 3,
"hispanicLatino": "N",
"hsAcademicGpa": null,
"instagramUrl": null,
"isActive": true,
"isAllowedBulkRegistrationByTrack": null,
"isBadAddress": false,
"isBadPhone": false,
"isClearinghouseDataBlockIndicator": false,
"isDdVeteran": false,
"isEftDefaultForStipends": false,
"isInDistrict": false,
"isSscrError11Received": false,
"lastActivityDate": null,
"lastInterestDate": null,
"lastModifiedDateTime": "2024/04/03 06:56:56",
"lastModifiedUserId": 3186,
"lastName": "Williams",
"lastNameFirstFour": "Will",
"lastStatementBeginDate": null,
"lastStatementCloseDate": null,
"lastStatementDate": null,
"leadDate": "2022/08/10 12:46:00",
"leadSourceId": 691,
"leadTypeId": 3,
"linkedInUrl": null,
"maidenName": "",
"maritalStatusId": 1,
"mi": "E",
"middleName": "Eratosthenes",
"mobilePhoneNumber": " ",
"nationalityId": 15,
"nickName": "",
"niStudent": false,
"note": " ",
"originalAssignedAdmissionsRepId": 66,
"originalExpectedStartDate": null,
"originalStartDate": "2023/08/29 13:44:30",
"otherEmailAddress": "",
"otherLanguageFirstName": null,
"otherLanguageLastName": null,
"otherLanguageMiddleName": null,
"otherLanguageStudentFullName": null,
"otherPhoneNumber": "",
"personId": 853,
"phoneNumber": "(112) 323-4345",
"pin": 9023,
"postalCode": "75053",
"postalCodeFirstThree": "750",
"preferredContactType": "Ph",
"preferredName": null,
"previousEducationGpa": null,
"previousEducationId": 7,
"programGroupId": 6,
"programId": 10,
"rawFirstName": "Chase",
"rawLastName": "Williams",
"rawPhoneNumber": "1123234345",
"rowVersion": "AAAAAAMotC4=",
"schoolStatusId": 14,
"shiftId": 2,
"smsServiceProviderId": null,
"sourceSystem": "C",
"ssn": "343-27-9023",
"startDate": "2022/08/22 00:00:00",
"state": "TX",
"statementComment": " ",
"streetAddress": "46 Applewood Street",
"streetAddress2": null,
"studentFullName": null,
"studentIdentifier": null,
"studentNumber": "749",
"subscribeToSms": false,
"suffix": null,
"suffixId": null,
"titleId": 1,
"twitterUrl": null,
"veteran": "",
"workPhoneNumber": "",
"workPhoneNumberExtension": "",
"originalState": "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",
"secureState": "H4sIAAAAAAAEAD3MQQrCMBAAwK9I7mZTeysqeFbpoSJel5C0C01Ssisxvl6s4ANm9qecsfb+7Ood56frPUumOGKst7q4zSvMkQ9qElk6ALaTC8g6kM2JkxdtU4CdMS00BgaXCWd6o1CKsMasfkNH/6OUokurUx6/sIHH9TKs7ZYiC0brFBw/juQnSpcAAAA=",
"extendedProperties": [],
"entityState": 3
}
}
```

## Additional notes:

### Implementation of Save operation

Not every entity has the Save operation implemented. As a general rule you can use to determine if the Save operation is implemented is to look at the other operations for that entity in the Swagger documentation. If there is another operation listed that has a summary description related to updating existing records then the Save operation should not be utilized. If you have any doubts, please send an email to Developers@anthology.com requesting clarification on which endpoint to use for updating an existing record for an entity.

### EntityState property

EntityState is a property that exists on the base entity class that every entity inherits from. This is an enum property with the following valid values:

    0= Record is being added
    1= Record is being deleted
    2= Record is being modified
    3= Record is unchanged

The value provided in this property may or may not impact the execution logic of the API you are calling. The use of this property in the API execution logic is not consistent across all of the Delete, Save and SaveNew operations. It is recommended that this property be populated correctly to align with the action that is occurring to ensure expected behavior in the API if there is dependent execution logic on this property.

<AuthorBox frontMatter={frontMatter}/>
