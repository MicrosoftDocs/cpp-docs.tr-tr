---
title: SET_PARAM_TYPE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- SET_PARAM_TYPE
dev_langs:
- C++
helpviewer_keywords:
- SET_PARAM_TYPE macro
ms.assetid: 85979070-2d55-4c67-94b1-9b9058babc59
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9ab4884032425f13c2cc506d6e66c955eb439f7d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="setparamtype"></a>SET_PARAM_TYPE
Belirtir `COLUMN_ENTRY` izleyin makroları `SET_PARAM_TYPE` makrosu giriş, çıkış veya giriş/çıkış.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
SET_PARAM_TYPE(type)  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `type`  
 [in] İçin parametre türü.  
  
## <a name="remarks"></a>Açıklamalar  
 Sağlayıcılar, temel alınan veri kaynağı tarafından desteklenen parametresi giriş/çıkış türlerini destekler. Bir veya daha fazla bileşimini türüdür **DBPARAMIO** değerleri (bkz [IAccessor::CreateAccessor'ı yapıları](https://msdn.microsoft.com/en-us/library/ms716845.aspx) içinde *OLE DB Programcının Başvurusu*):  
  
-   **DBPARAMIO_NOTPARAM** erişimci hiç parametre yok. Genellikle, ayarladığınız **eParamIO** bu değere satır Erişimcilerde parametreleri göz ardı edilir kullanıcıyı şu aralıklarla uyar.  
  
-   **DBPARAMIO_INPUT** giriş parametresi.  
  
-   **DBPARAMIO_OUTPUT** çıktı parametresi.  
  
-   **DBPARAMIO_INPUT &#124; DBPARAMIO_OUTPUT** bir girdi ve çıktı parametresi parametresidir.  
  
## <a name="example"></a>Örnek  
```
cpp  
class CArtistsProperty
{
public:
   short m_nReturn;
   short m_nAge;
   TCHAR m_szFirstName[21];
   TCHAR m_szLastName[31];

BEGIN_PARAM_MAP(CArtistsProperty)
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)
   COLUMN_ENTRY(1, m_nReturn)
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(2, m_nAge)
END_PARAM_MAP()

BEGIN_COLUMN_MAP(CArtistsProperty)
   COLUMN_ENTRY(1, m_szFirstName)
   COLUMN_ENTRY(2, m_szLastName)
END_COLUMN_MAP()

   HRESULT OpenDataSource()
   {
      CDataSource _db;
      _db.Open();
      return m_session.Open(_db);
   }

   void CloseDataSource()
   {
      m_session.Close();
   }

   CSession m_session;

   DEFINE_COMMAND_EX(CArtistsProperty, L" \
      { ? = SELECT Age FROM Artists WHERE Age < ? }")
};
``` 
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları için Makrolar ve Genel İşlevler](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)