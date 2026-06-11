# s3-poc

A Mule 4 Proof of Concept (POC) application designed to integrate with AWS S3 services. 

## Prerequisites

Before running this application, ensure you have the following installed and configured:
* **Java:** JDK 17
* **Anypoint Studio:** Version 7.x or later
* **Mule Runtime:** Version 4.x or later
* **Maven:** 3.8.x or later (configured with Java 17)
* **AWS Account:** With access to an S3 bucket and valid AWS credentials (`Access Key` and `Secret Key`)

## Getting Started

### 1. Clone the Repository
```bash
git clone [https://github.com/rasthanaMule/s3-poc.git](https://github.com/rasthanaMule/s3-poc.git)
cd s3-poc

3. Run the Application Locally
Via Command Line (Maven):
Ensure your JAVA_HOME points to JDK 17, then run:
mvn clean mule:run

curl -X GET http://localhost:8081/list-files

Expected Response
A successful execution should return a confirmation or the payload returned by your S3 connector
configuration (e.g., a list of bucket objects or a file upload confirmation status).

[
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 0,
    "eTag": "\"d41d8cd98f00b204e9800998ecf8427e\"",
    "lastModified": "2026-06-02T21:11:39",
    "key": "Resources/"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 206128,
    "eTag": "\"55abc87a3d12100838a50fa6da9b9656\"",
    "lastModified": "2026-06-03T15:34:55",
    "key": "Resources/20240618_RRS Regulatory Terms_Final.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 9481360,
    "eTag": "\"24c3fe2b2d2768d82b51a1443ba1e680\"",
    "lastModified": "2026-06-03T15:39:03",
    "key": "Resources/ARDR Recommended Minimum Standards-21JUL25.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 12650999,
    "eTag": "\"44da6c87757b0783bad717b38c19af35\"",
    "lastModified": "2026-06-03T15:39:31",
    "key": "Resources/ARDR_Example_Figures.ppkx"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 191,
    "eTag": "\"a32b0d79d5755cfd8a792cb5df3071c6\"",
    "lastModified": "2026-06-03T15:35:01",
    "key": "Resources/Adjoining_Property_Owner_Bulk_Upload_CSV_Template.csv"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 316990,
    "eTag": "\"626bd5d49feaac61ecb3f689e69ed236\"",
    "lastModified": "2026-06-03T15:35:01",
    "key": "Resources/Appx_A1_Property_Owners.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 274817,
    "eTag": "\"d80ab282ef524c1b4589166828113b9c\"",
    "lastModified": "2026-06-03T15:35:01",
    "key": "Resources/Appx_A2_Adjoining_Property_Owners.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 917261,
    "eTag": "\"145477f6ef2971820a21f05d9a1ebbe2\"",
    "lastModified": "2026-06-03T15:35:01",
    "key": "Resources/Appx_B_Aquatic_Resources.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 1045988,
    "eTag": "\"0a2015e8d36be92c809fbf2d0766bb8c\"",
    "lastModified": "2026-06-03T15:35:03",
    "key": "Resources/Appx_C_Impacts.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 843371,
    "eTag": "\"d75e6561c85acea274c5d697fb46b4d3\"",
    "lastModified": "2026-06-03T15:35:06",
    "key": "Resources/Appx_D1_MB_ILF.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 261443,
    "eTag": "\"12a95cb02b566cd4cd8fd50b20aef097\"",
    "lastModified": "2026-06-03T15:35:06",
    "key": "Resources/Appx_D2_PRM.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 849004,
    "eTag": "\"9db6da580e2944bfba40a2ab0505e95d\"",
    "lastModified": "2026-06-03T15:35:06",
    "key": "Resources/Appx_E_Dredging.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 825511,
    "eTag": "\"6a2939f186271fd92a9de1adf9a93412\"",
    "lastModified": "2026-06-03T15:35:06",
    "key": "Resources/Appx_F_Shoreline_Stabilization.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 2040942,
    "eTag": "\"851481e2de315698359df533b5429012\"",
    "lastModified": "2026-06-03T15:35:06",
    "key": "Resources/Appx_G_Pile_Driving.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 134760,
    "eTag": "\"b41c095d1132a1e844dd361fab930eaf\"",
    "lastModified": "2026-06-03T15:35:59",
    "key": "Resources/Appx_H_Supporting_Files.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 879338,
    "eTag": "\"2f7e605205b7bb85bb88c516a9e4cd74\"",
    "lastModified": "2026-06-03T15:37:00",
    "key": "Resources/Aquatic Resource Geodatabase Quick Guide V2.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 74949,
    "eTag": "\"0eb2730530444e85ddbedbc2ca690f8e\"",
    "lastModified": "2026-06-03T15:35:59",
    "key": "Resources/Aquatic_Resource_Bulk_Upload_10092025.gdb.zip"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 230615,
    "eTag": "\"dad052d8f1d49895a668f547bdc067cd\"",
    "lastModified": "2026-06-03T15:35:59",
    "key": "Resources/Aquatic_Resource_Bulk_Upload_Guide.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 164,
    "eTag": "\"2221fc65ccba196a5707d7de6955af91\"",
    "lastModified": "2026-06-03T15:35:59",
    "key": "Resources/Aquatic_Resource_Bulk_Upload_Template.csv"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 536351,
    "eTag": "\"bd56cb7b37293d5d4c833c52ada33bb1\"",
    "lastModified": "2026-06-03T15:36:08",
    "key": "Resources/District_Specific_Information_14MAY2024.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 279470,
    "eTag": "\"dfcea802d0b5ffc1437b9b283df8bb16\"",
    "lastModified": "2026-06-03T15:58:57",
    "key": "Resources/ENG_4345_Individual_Permit.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 569981,
    "eTag": "\"9909c7fc4cd09d1a72a9fb3c91095e66\"",
    "lastModified": "2026-06-03T15:39:32",
    "key": "Resources/ENG_6082_Nationwide_Permit.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 425654,
    "eTag": "\"3c00df9a384945762305e5c91e1e5a60\"",
    "lastModified": "2026-06-03T15:40:08",
    "key": "Resources/ENG_6247_Jurisdictional_Determination.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 351153,
    "eTag": "\"9d7848e4744be2a90a59184747f83724\"",
    "lastModified": "2026-06-03T15:42:34",
    "key": "Resources/ENG_6284_Violation_Complaint.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 352508,
    "eTag": "\"8bd94e21a842bdc0d11f6a7e8b1ace50\"",
    "lastModified": "2026-06-03T15:42:32",
    "key": "Resources/ENG_6286_Pre_Application.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 60483,
    "eTag": "\"fcb32388c8f92529932586cdead82931\"",
    "lastModified": "2026-06-03T15:42:32",
    "key": "Resources/ENG_6294_Right_Of_Entry.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 46464,
    "eTag": "\"61d4e82af3542ca105d75e63fc2b5907\"",
    "lastModified": "2026-06-03T15:43:04",
    "key": "Resources/ENG_6295_Agent_Authorization.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 297552,
    "eTag": "\"bf084d852f428086558d9ce9a4da8c0f\"",
    "lastModified": "2026-06-03T15:34:41",
    "key": "Resources/GNSS Guide for Mapping Aquatic Resources-21JUL25.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 182292,
    "eTag": "\"0bf5bb6c63a360203b355ab44eb07238\"",
    "lastModified": "2026-06-03T15:34:35",
    "key": "Resources/IP_Additional_Info.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 332,
    "eTag": "\"244dbefdf327b2f3cd2bcb6b78acb448\"",
    "lastModified": "2026-06-03T15:34:35",
    "key": "Resources/Impact_Bulk_Upload_CSV_Template.csv"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 561961,
    "eTag": "\"fd1694f6370eebf7ecca9b5fcebeb657\"",
    "lastModified": "2026-06-03T15:34:35",
    "key": "Resources/Impacts_Mitigation_Bulk_Upload_Guide.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 190894,
    "eTag": "\"6dfe44f64ba693bfad6123b5c4acb51a\"",
    "lastModified": "2026-06-03T15:34:35",
    "key": "Resources/JD_Additional_info.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 0,
    "eTag": "\"d41d8cd98f00b204e9800998ecf8427e\"",
    "lastModified": "2026-06-03T16:00:25",
    "key": "Resources/JPADocuments/"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 400209,
    "eTag": "\"e8fc4f5faa29fccbcdb7293289489f6a\"",
    "lastModified": "2026-06-03T15:34:41",
    "key": "Resources/JPA_Districts_14MAY2024.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 439574,
    "eTag": "\"97e6d20bcee3293a2452c822d16aea57\"",
    "lastModified": "2026-06-03T15:34:41",
    "key": "Resources/Login_gov_guide.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 188,
    "eTag": "\"b886af3e598cb083c3d87a79623c46ea\"",
    "lastModified": "2026-06-03T15:34:41",
    "key": "Resources/Mitigation_Bank_Inlieu_Fee_Bulk_Upload_CSV_Template.csv"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 328,
    "eTag": "\"9d4529ed349290c703620bd5f2cff1bf\"",
    "lastModified": "2026-06-03T15:34:41",
    "key": "Resources/Permittee_Responsible_Mitigation_Bulk_Upload_CSV_Template.csv"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 532,
    "eTag": "\"a2c24c6e02be48205d13c3b6b35779e4\"",
    "lastModified": "2026-06-03T15:34:45",
    "key": "Resources/Property_Owner_Bulk_Upload_CSV_Template.csv"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 1318514,
    "eTag": "\"3655fb4d6aadd48223d42382ea1fcaa5\"",
    "lastModified": "2026-06-03T15:34:45",
    "key": "Resources/Sample Drawing_Bank Stabilization (Bioengineered) 20240515.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 803740,
    "eTag": "\"b73bd773d44e171c4dd0252f215d937b\"",
    "lastModified": "2026-06-03T15:34:45",
    "key": "Resources/Sample Drawing_Bank Stabilization (Riprap)_20240515.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 567170,
    "eTag": "\"f07403d10a3c29a0f4f558256d14501b\"",
    "lastModified": "2026-06-03T15:34:55",
    "key": "Resources/Sample Drawing_Culvert_20240318.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 641117,
    "eTag": "\"1ec811aa9c5ed680e5bcbd13cc23e20a\"",
    "lastModified": "2026-06-03T15:34:46",
    "key": "Resources/Sample Drawing_Dock_20240226.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 494209,
    "eTag": "\"cdb81649b0d9ccecf9b6da33f308e695\"",
    "lastModified": "2026-06-03T15:34:55",
    "key": "Resources/Sample Drawing_Stream Crossing_20240304.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 580492,
    "eTag": "\"7a1f910175fe9800537fc92b64d44439\"",
    "lastModified": "2026-06-03T15:34:55",
    "key": "Resources/Sample Drawing_Wetland Fill for House_20240514.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 1059488,
    "eTag": "\"0458ed42992b7284545bedb43e83cd61\"",
    "lastModified": "2026-06-03T15:34:55",
    "key": "Resources/Sample Drawing_Wetland Fill for Road_20240426.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 0,
    "eTag": "\"d41d8cd98f00b204e9800998ecf8427e\"",
    "lastModified": "2026-06-03T21:57:17",
    "key": "Templates/"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 71854,
    "eTag": "\"6ca508412e857ddb63914626914d7cac\"",
    "lastModified": "2026-06-03T21:58:25",
    "key": "Templates/Aquatic_Resource_Bulk_Upload.gdb.zip"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 551878,
    "eTag": "\"7189d886609230beea127dbae8cf5511\"",
    "lastModified": "2026-06-03T21:58:25",
    "key": "Templates/Aquatic_Resource_Bulk_Upload_Guide.pdf"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 10473,
    "eTag": "\"3d9e284f35a259dcba675a8799f57b36\"",
    "lastModified": "2026-06-03T21:58:25",
    "key": "Templates/Aquatic_Resource_Bulk_Upload_Template.xlsx"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 282700,
    "eTag": "\"e3068d5bb0c8a70cfa51579b01e2991a\"",
    "lastModified": "2026-06-03T21:58:25",
    "key": "Templates/ORM_Upload_Sheet_Consolidated_Amended_2023Rule_20230921.xlsm"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 283317,
    "eTag": "\"048a834d6521d3399c07578d26ad9bda\"",
    "lastModified": "2026-06-03T21:58:25",
    "key": "Templates/ORM_Upload_Sheet_Consolidated_Pre2015_Post_Sackett_20230921.xlsm"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 24202,
    "eTag": "\"46dc47311fa4f9ccb4ddc890e9f5b1d2\"",
    "lastModified": "2026-06-03T21:59:02",
    "key": "Templates/ProjectArea_BLANK.gdb.zip"
  },
  {
    "owner": {
      "id": "69c4c9b404ee7a9269d56a9bd6422920b889f5a29431faae78a88ca302a4da25"
    },
    "checksumAlgorithm": [
      "CRC64NVME"
    ],
    "storageClass": "STANDARD",
    "size": 13925,
    "eTag": "\"fde76a8cc3ecea66754f7a05e947bd81\"",
    "lastModified": "2026-06-03T21:59:02",
    "key": "Templates/Property_Owner_Template_v1.xlsx"
  }
]
