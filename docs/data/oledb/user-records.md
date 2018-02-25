---
title: "Kullanıcı kayıtları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COLUMN_ENTRY_MAP
dev_langs:
- C++
helpviewer_keywords:
- rowsets [C++], accessors
- COLUMN_ENTRY macro
- COLUMN_ENTRY_MAP macro
- user records, OLE DB consumer templates
- OLE DB consumer templates, user records
- CAccessor class, example
- BEGIN_ACCESSOR_MAP macro
- accessors [C++], rowsets
- accessors [C++], static
- BEGIN_ACCESSOR macro, example
ms.assetid: 2de9e5eb-53ce-42b1-80fa-57d46600a80c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: faead3ec85fc799abd26613979f7611c9159cc9b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="user-records"></a>Kullanıcı Kayıtları
Statik erişimci kullanmak için (öğesinden türetilen bir erişimci **CAccessor)**, bir kullanıcı kaydı, tüketici olmalıdır. Kullanıcı kaydını tanıtıcı giriş veya çıkış veri öğeleri içeren bir C++ sınıfıdır. ATL OLE DB Tüketici Sihirbazı tüketici için bir kullanıcı kaydı oluşturur. Komutları işleme gibi isteğe bağlı görevleri için kullanıcı kayıt yöntemleri ekleyebilirsiniz.  
  
 Aşağıdaki kod komutları işleyen bir kayıt örneği gösterir. Kullanıcı kaydındaki `BEGIN_COLUMN_MAP` sağlayıcıdan tüketiciye geçen veri satır kümesini temsil eder. `BEGIN_PARAM_MAP` Komut parametreleri kümesini temsil eder. Bu örnekte bir [CCommand](../../data/oledb/ccommand-class.md) komut parametrelerini işlemek için sınıf. Eşleme girdilerini veri üyeleri sınıfın her örneği için bellek bir bitişik bloğuna uzaklıkları temsil eder. `COLUMN_ENTRY` Makroları karşılık `PROVIDER_COLUMN_ENTRY` makroları sağlayıcı tarafındaki.  
  
 Hakkında daha fazla bilgi için **COLUMN_MAP** ve **PARAM_MAP** makrolar bkz [OLE DB Tüketici Şablonları için makrolar](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md).  
  
```  
class CArtists  
{  
public:  
// Data Elements  
   CHAR m_szFirstName[20];  
   CHAR m_szLastName[30];  
   short m_nAge;  
  
// Column binding map  
BEGIN_COLUMN_MAP(CArtists)  
   COLUMN_ENTRY(1, m_szFirstName)  
   COLUMN_ENTRY(2, m_szLastName)  
   COLUMN_ENTRY(3, m_nAge)  
END_COLUMN_MAP()  
  
// Parameter binding map  
BEGIN_PARAM_MAP(CArtists)  
   COLUMN_ENTRY(1, m_nAge)  
END_PARAM_MAP()  
};  
```  
  
## <a name="wizard-generated-user-records"></a>Sihirbaz tarafından oluşturulan kullanıcı kayıtları  
 Tüketici oluşturmak için ATL OLE DB Tüketici Sihirbazı'nı kullanırsanız, OLE DB Şablonları veya OLE DB öznitelikleri kullanma seçeneği vardır. Oluşturulan kodun her durumda farklıdır. Bu kodu hakkında daha fazla bilgi için bkz: [Tüketici Sihirbazı tarafından oluşturulan sınıflar](../../data/oledb/consumer-wizard-generated-classes.md).  
  
## <a name="user-record-support-for-multiple-accessors"></a>Çoklu erişimci için kullanıcı kaydı desteği  
 İçinde çoklu erişimci kullanmanızı gerektiren senaryolar hakkında ayrıntılı bilgi için bkz: [bir satır kümesi üzerinde Çoklu Erişimci Kullanma](../../data/oledb/using-multiple-accessors-on-a-rowset.md).  
  
 Aşağıdaki örnek satır kümesinde çoklu erişimci desteklemek için değiştirilen kullanıcı kaydını gösterir. Yerine `BEGIN_COLUMN_MAP` ve `END_COLUMN_MAP`, kullandığı [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md) ve [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) her erişimcisi için. `BEGIN_ACCESSOR` Makrosu erişimci sayısını (sapma sıfırdan) ve erişimcinin otomatik erişimci olup olmadığını belirtir. Erişimciler `GetData` otomatik olarak yapılan bir çağrı veri almak için [MoveNext](../../data/oledb/crowset-movenext.md). Otomatik olmayan erişimciler açıkça verileri almak üzere gerektirir. Almak için her kayıt için istemeyebilirsiniz büyük veri alanına (örneğin, bir bit eşlem görüntüsü) bağlıyorsanız otomatik olmayan erişimci kullanın.  
  
```  
class CMultiArtists  
{  
public:  
// Data Elements  
   CHAR m_szFirstName[20];  
   CHAR m_szLastName[30];  
   short m_nAge;  
  
// Column binding map  
BEGIN_ACCESSOR_MAP(CMultiArtists, 2)  
   BEGIN_ACCESSOR(0, true)    // true specifies an auto accessor  
    COLUMN_ENTRY(1, m_szFirstName)  
    COLUMN_ENTRY(2, m_szLastName)  
   END_ACCESSOR()  
   BEGIN_ACCESSOR(1, false)   // false specifies a manual accessor  
    COLUMN_ENTRY(3, m_nAge)  
   END_ACCESSOR()  
END_ACCESSOR_MAP()  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)