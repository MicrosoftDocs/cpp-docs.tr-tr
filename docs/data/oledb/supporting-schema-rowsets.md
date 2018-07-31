---
title: Şema satır kümelerini destekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- schema rowsets
- OLE DB consumer templates, schema rowsets
- OLE DB providers, schema rowsets
- OLE DB, schema rowsets
ms.assetid: 71c5e14b-6e33-4502-a2d9-a1dc6d6e9ba0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7c0468a9df7b79e79b3e20074c43fc1621058d71
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339711"
---
# <a name="supporting-schema-rowsets"></a>Şema Satır Kümelerini Destekleme
Şema satır kümeleri, temel alınan yapısını veya şema farkında olmadan bir veri deposu hakkında bilgi edinmek tüketiciler izin verir. Örneğin, bir veri deposunu okuma tarafından şemanın bilgi emin olmanın bir yolu nedenle kullanıcı tanımlı bir hiyerarşi halinde düzenlenmiş tablolar olabilir. (Başka bir örnek olarak, Visual C++ sihirbazları, tüketicinin için erişimciler üretmek için şema satır kümeleri kullandığını unutmayın.) Bunu yapmak tüketici izin vermek için sağlayıcının oturum nesnesi yöntemleri gösterir [IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx) arabirimi. Visual C++ uygulamalarında kullandığınız [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) uygulamak için sınıfı `IDBSchemaRowset`.  
  
 `IDBSchemaRowsetImpl` Aşağıdaki yöntemleri destekler:  
  
-   [CheckRestrictions](../../data/oledb/idbschemarowsetimpl-checkrestrictions.md) kısıtlamaları şeması satır kümesi karşı geçerliliğini denetler.  
  
-   [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md) şablon parametresi tarafından belirtilen nesne için bir COM nesnesi oluşturan işlevi uygular.  
  
-   [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md) destekleyen bir belirli şeması satır kümesi üzerinde hangi kısıtlamalar belirtir.  
  
-   [IDBSchemaRowset::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md) (arabiriminden devralınan) şeması satır kümesi döndürür.  
  
-   [GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md) şema satır kümeleri listesi tarafından erişilebilen döndürür `IDBSchemaRowsetImpl::GetRowset` (arabiriminden devralınan).  
  
## <a name="atl-ole-db-provider-wizard-support"></a>ATL OLE DB sağlayıcısı Sihirbazı desteği  
 ATL OLE DB sağlayıcısı Sihirbazı üç şema sınıfları oturumu üstbilgi dosyası oluşturur:  
  
-   **C** *ShortName* **SessionTRSchemaRowset**  
  
-   **C** *ShortName* **SessionColSchemaRowset**  
  
-   **C** *ShortName* **SessionPTSchemaRowset**  
  
 Bu sınıflar için şema bilgileri tüketici isteklerine yanıt vermek; OLE DB belirtimi, bu üç şema satır kümeleri desteklenen gerektiğini unutmayın:  
  
-   **C** *ShortName* **SessionTRSchemaRowset** için tablo bilgileri isteklerini işler ( `DBSCHEMA_TABLES` şeması satır kümesi).  
  
-   **C** *ShortName* **SessionColSchemaRowset** sütun bilgisi isteklerini işler ( `DBSCHEMA_COLUMNS` şeması satır kümesi). Sihirbaz, bu sınıflar bir DOS sağlayıcısı için şema bilgileri döndürmek için örnek uygulamaları sağlar.  
  
-   **C** *ShortName* **SessionPTSchemaRowset** için şema bilgileri sağlayıcısı türü hakkındaki istekleri işler ( `DBSCHEMA_PROVIDER_TYPES` şeması satır kümesi). Sihirbaz tarafından sağlanan varsayılan uygulamasını döndürür `S_OK`.  
  
 Şema bilgileri sağlayıcınıza uygun işlemek için bu sınıfların özelleştirebilirsiniz:  
  
-   İçinde **C***ShortName***SessionTRSchemaRowset**, katalog, tablo ve açıklama alanları doldurmanız gerekir (`trData.m_szType`, `trData.m_szTable`, ve `trData.m_szDesc`). Sihirbazın ürettiği örnek yalnızca bir satır (tablo) kullanır. Diğer sağlayıcılar, birden fazla tablo döndürebilir.  
  
-   İçinde **C***ShortName***SessionColSchemaRowset**, tablonun adını geçirdiğiniz bir `DBID`.  
  
## <a name="setting-restrictions"></a>Kısıtlamalarını ayarlama  
 Şema satır kümesi desteği önemli bir kavramdır kullanarak bunu kısıtlamaları Ayarlıyor `SetRestrictions`. Kısıtlamalar yalnızca eşleşen satırları getirilecek tüketiciler izin ver (örneğin, tüm sütunları tabloda "MyTable" Bul). Kısıtlamaları isteğe bağlıdır ve durumda hiçbiri desteklenir (varsayılan), tüm veriler her zaman döndürülür. Kısıtlamaları destekleyen bir sağlayıcı örneği için bkz: [UpdatePV](http://msdn.microsoft.com/c8bed873-223c-4a7d-af55-f90138c6f38f) örnek.  
  
## <a name="setting-up-the-schema-map"></a>Şema eşleme ayarlama  
 Bir şema eşlemesine UpdatePV Session.h'deki bunun gibi ayarlayın:  
  
```  
BEGIN_SCHEMA_MAP(CUpdateSession)  
    SCHEMA_ENTRY(DBSCHEMA_TABLES, CUpdateSessionTRSchemaRowset)  
    SCHEMA_ENTRY(DBSCHEMA_COLUMNS, CUpdateSessionColSchemaRowset)  
    SCHEMA_ENTRY(DBSCHEMA_PROVIDER_TYPES, CUpdateSessionPTSchemaRowset)  
END_SCHEMA_MAP()  
```  
  
 Desteklemek için `IDBSchemaRowset`, desteklemeniz gereken `DBSCHEMA_TABLES`, `DBSCHEMA_COLUMNS`, ve `DBSCHEMA_PROVIDER_TYPES`. İstediğiniz kadar ek şema satır kümeleri ekleyebilirsiniz.  
  
 Şema satır kümesi sınıfıyla bildirmek bir `Execute` yöntemi gibi `CUpdateSessionTRSchemaRowset` UpdatePV:  
  
```  
class CUpdateSessionTRSchemaRowset :   
    public CSchemaRowsetImpl < CUpdateSessionTRSchemaRowset,   
                              CTABLESRow, CUpdateSession >  
...  
// Execute looks like this; what pointers does the consumer use?  
    HRESULT Execute(DBROWCOUNT* pcRowsAffected,   
                    ULONG cRestrictions, const VARIANT* rgRestrictions)  
```  
  
 Unutmayın `CUpdateSession` devraldığı `IDBSchemaRowsetImpl`, yöntemlerinin yönetilmesi kısıtlama vardır. Kullanarak `CSchemaRowsetImpl`, üç alt sınıfları (şema eşlemede listelenmiştir) bildirmek: `CUpdateSessionTRSchemaRowset`, `CUpdateSessionColSchemaRowset`, ve `CUpdateSessionPTSchemaRowset`. Bu alt sınıfların her bir `Execute` kısıtlamaları (arama ölçütleri) ilgili bir dizi işleyen yöntem. Her `Execute` yöntemi değerlerini karşılaştırır `cRestrictions` ve `rgRestrictions` parametreleri. Bu parametreleri açıklamasına bakın [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md).  
  
 İlgili kısıtlamaları karşılık gelen bir belirli şeması satır kümesi için daha fazla bilgi için tablosu şeması satır kümesi GUID'leri başvurun içinde [IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx) içinde *OLE DB Programcının Başvurusu* içinde Windows SDK'sı.  
  
 Örneğin, desteklenen **TABLE_NAME** kısıtlaması `DBSCHEMA_TABLES`, aşağıdakileri yapmanız gerekir:  
  
 İlk olarak, arama `DBSCHEMA_TABLES` ve dört kısıtlamaları (sırasıyla) destekler.  
  
|Şema satır kümesi kısıtlama|Kısıtlama değeri|  
|-------------------------------|-----------------------|  
|**TABLE_CATALOG**|0x1 (ikili 1)|  
|**TABLE_SCHEMA**|0x2 (ikili 10)|  
|**TABLE_NAME**|0x4 (ikili 100)|  
|**TABLE_TYPE**|0x8 (ikili 1000)|  
  
 Ardından, her kısıtlama için bir bit olduğuna dikkat edin. Desteklemek istediğiniz çünkü **TABLE_NAME** yalnızca 0x4 geri `rgRestrictions` öğesi. Destekleniyorsa, **TABLE_CATALOG** ve **TABLE_NAME**, 0x5 (ikili 101) döndürecektir.  
  
 Varsayılan olarak, herhangi bir istek için 0 (herhangi bir kısıtlama desteklemez) uygulamasını döndürür. UpdatePV kısıtlamaları destekleyen sağlayıcı örneğidir.  
  
### <a name="example"></a>Örnek  
 Bu kod alınır [UpdatePV](http://msdn.microsoft.com/c8bed873-223c-4a7d-af55-f90138c6f38f) örnek. UpdatePv üç gerekli şema satır kümeleri destekler: `DBSCHEMA_TABLES`, `DBSCHEMA_COLUMNS`, ve `DBSCHEMA_PROVIDER_TYPES`. Uygulama konusunda şema desteği sağlayıcınızda uygulamak nasıl bir örnek olarak, bu konuda, alan `DBSCHEMA_TABLE` satır kümesi.  
  
> [!NOTE]
>  Örnek kod, ne burada listelenen öğesinden farklı olabilir; Örnek kod daha güncel bir sürüm olarak göz önüne almalısınız.  
  
 İlk adımı şema desteği eklemeyi desteklemek için oluşturacağınız hangi kısıtlamaları belirlemektir. OLE DB belirtimi tanımı için bakmak hangi kısıtlamaları, şeması satır kümesi için kullanılabilir olduğunu belirlemek için `IDBSchemaRowset`. Ana tanımı şema satır kümesi adı, kısıtlama sayısı ve kısıtlama sütunlarını içeren bir tablo görürsünüz. Kısıtlamaları ve kısıtlama sütun sayısını not edin ve desteklemek için istediğiniz şeması satır kümesi seçin. Örneğin, `DBSCHEMA_TABLES` dört kısıtlamaları destekler (**TABLE_CATALOG**, **TABLE_SCHEMA**, **TABLE_NAME**, ve **TABLE_TYPE** ):  
  
```cpp  
void SetRestrictions(ULONG cRestrictions, GUID* rguidSchema,   
   ULONG* rgRestrictions)  
{  
    for (ULONG l=0; l<cRestrictions; l++)  
    {  
        if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_TABLES))  
            rgRestrictions[l] = 0x0C;  
        else if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_COLUMNS))  
                 rgRestrictions[l] = 0x04;  
             else if (InlineIsEqualGUID(rguidSchema[l],  
                                        DBSCHEMA_PROVIDER_TYPES))  
                      rgRestrictions[l] = 0x00;  
   }  
}  
```  
  
 Bir bit her kısıtlama sütunu temsil eder. Bir kısıtlama desteklemek istiyorsanız (diğer bir deyişle, sorgulayabilirsiniz), söz konusu bit 1 olarak ayarlayın. Kısıtlama desteklemek istemiyorsanız, söz konusu bit sıfır olarak ayarlayın. Yukarıdaki kod satırından UpdatePV destekler **TABLE_NAME** ve **TABLE_TYPE** kısıtlamalar `DBSCHEMA_TABLES` satır kümesi. (Bit maskesi 100) üçüncü ve dördüncü (bit maskesi 1000) kısıtlamaları şunlardır. Bu nedenle UpdatePv için bit maskesi 1100 (veya 0x0C) gereklidir:  
  
```  
if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_TABLES))  
    rgRestrictions[l] = 0x0C;  
```  
  
 Aşağıdaki `Execute` işlev, normal satır kümeleri benzer. Üç bağımsız değişkeni vardır: *pcRowsAffected*, *cRestrictions*, ve *rgRestrictions*. *PcRowsAffected* değişkendir sağlayıcı şeması satır kümesi içinde satır sayısını döndürebilir çıkış parametresi. *CRestrictions* tüketici tarafından sağlayıcısına geçirilen kısıtlamalar sayısını içeren bir parametredir giriş. *RgRestrictions* parametresi, bir dizi `VARIANT` kısıtlama değerleri içeren bir değerler.  
  
```  
HRESULT Execute(DBROWCOUNT* pcRowsAffected, ULONG cRestrictions,   
                const VARIANT* rgRestrictions)  
```  
  
 `cRestrictions` Değişkeni sağlayıcı bunları destekleyip bağımsız olarak bir şeması satır kümesi için kısıtlamalar toplam sayısını temel alır. UpdatePv (üçüncü ve dördüncü) iki kısıtlama desteklediğinden, bu kod yalnızca arayan bir `cRestrictions` üç eşit veya büyük değer.  
  
 Değeri **TABLE_NAME** kısıtlama depolanan `rgRestrictions[2]` (yeniden üçüncü kısıtlamayı sıfır tabanlı bir dizi 2'dir). Kısıtlama gerçekten desteklemek için VT_EMPTY olmadığını denetlemek gerekir. VT_NULL VT_EMPTY için eşit olmadığını unutmayın. VT_NULL geçerli bir kısıtlama değeri belirtir.  
  
 Bir metin dosyasına tam yol adı tablo adı UpdatePv tanımıdır. Kısıtlama değerini ayıklayın ve ardından dosyanın gerçekten var olmadığından emin olmak için dosyayı açmayı deneyin. Dosya mevcut değilse S_OK döndürür. Bu biraz geriye doğru görünebilir ancak kodun hangi tüketici gerçekten söylüyor belirtilen ad tarafından desteklenen hiçbir tablo olduğunu değildir. S_OK dönüş doğru bir şekilde yürütülen kod anlamına gelir.  
  
```cpp  
USES_CONVERSION;  
enum {  
            sizeOfszFile = 255  
};  
CTABLESRow  trData;  
FILE        *pFile = NULL;  
TCHAR       szFile[ sizeOfszFile ];  
errcode     err = 0;  
  
// Handle any restrictions sent to us. This only handles  
// the TABLE_NAME & TABLE_TYPE restictions (the 3rd and 4th   
// restrictions in DBSCHEMA_TABLES...look in IDBSchemaRowsets   
// in part 2 of the prog. ref) so your restrictions are 0x08 & 0x04   
// for a total of (0x0C)  
if (cRestrictions >= 3 && rgRestrictions[2].vt != VT_EMPTY)  
{  
    CComBSTR bstrName = rgRestrictions[2].bstrVal;  
    if ((rgRestrictions[2].vt == VT_BSTR) && (bstrName != (BSTR)NULL))  
    {  
        // Check to see if the file exists  
        _tcscpy_s(&szFile[0], sizeOfszFile, OLE2T(bstrName));  
        if (szFile[0] == _T('\0') ||   
           ((err = _tfopen(&pFile, &szFile[0], _T("r"))) == 0))  
        {  
            return S_OK;// Their restriction was invalid return no data  
        }  
        else  
        {  
            fclose(pFile);  
        }  
    }  
}  
```  
  
 Dördüncü kısıtlama destekleme (**TABLE_TYPE**) üçüncü kısıtlamaya benzer. Değer VT_EMPTY olup olmadığını denetleyin. Bu kısıtlama yalnızca tablo türü döndürür **tablo**. İçin geçerli değerleri belirlemek için `DBSCHEMA_TABLES`, içinde ek B bakın *OLE DB Programcının Başvurusu* içinde **tabloları** satır kümesi bölümü.  
  
```  
// TABLE_TYPE restriction:  
if (cRestrictions >=4 && rgRestrictions[3].vt != VT_EMPTY)  
{  
    CComBSTR bstrType = rgRestrictions[3].bstrVal;  
    if ((rgRestrictions[3].vt == VT_BSTR) && (bstrType != (BSTR)NULL))  
    {  
        // This is kind of a blind restriction.  
        // This only actually supports  
        // TABLES so if you get anything else,   
        // just return an empty rowset.  
        if (_tcscmp(_T("TABLE"), OLE2T(bstrType)) != 0)  
            return S_OK;  
    }  
}  
```  
  
 Satır kümesi için bir satır girişi gerçekten oluşturduğunuz budur. Değişken `trData` karşılık gelen `CTABLESRow`, OLE DB sağlayıcı şablonları içinde tanımlanan bir yapı. `CTABLESRow` karşılık gelen **tabloları** satır kümesi tanımı OLE DB belirtiminin ek B. Yalnızca aynı anda yalnızca bir tablo destekleyebilir çünkü eklemek için bir satır var.  
  
```cpp  
// Bring over the data:  
wcspy_s(trData.m_szType, OLESTR("TABLE"), 5);  

wcspy_s(trData.m_szDesc, OLESTR("The Directory Table"), 19);  

wcsncpy_s(trData.m_szTable, T2OLE(szFile), _TRUNCATE());  
```  
  
 UpdatePV ayarlar yalnızca üç sütun: **TABLE_NAME**, **TABLE_TYPE**, ve **açıklama**. Uyguladığınızda bu bilgiler gerekeceğinden, iade ettiğiniz bilgi, sütunları not edin `GetDBStatus`:  
  
```cpp  
    _ATLTRY  
    {  
        m_rgRowData.Add(trData);  
    }  
    _ATLCATCHALL()  
    {  
        return E_OUTOFMEMORY;  
    }  
    //if (!m_rgRowData.Add(trData))  
    //    return E_OUTOFMEMORY;  
    *pcRowsAffected = 1;  
    return S_OK;  
}  
```  
  
 `GetDBStatus` İşlevi, şema satır kümesi doğru çalışması için çok önemlidir. Her sütun için veri döndürmeyen çünkü **tabloları** satır kümesi, hangi sütunların veri için geri dönün ve, bunu belirtmeniz gerekir.  
  
```cpp  
virtual DBSTATUS GetDBStatus(CSimpleRow* , ATLCOLUMNINFO* pColInfo)  
{  
    ATLASSERT(pColInfo != NULL);  
  
    switch(pColInfo->iOrdinal)  
    {  
    case 3:     // TABLE_NAME  
    case 4:     // TABLE_TYPE  
    case 6:     // DESCRIPTION  
        return DBSTATUS_S_OK;  
        break;  
    default:  
        return DBSTATUS_S_ISNULL;  
    break;  
    }  
}  
```  
  
 Çünkü, `Execute` işlevi için veri döndüren **TABLE_NAME**, **TABLE_TYPE**, ve **açıklama** alanlarını **tabloları**satır kümesi, OLE DB belirtiminin ek B bakın ve sıra sayıları 3, 4 ve 6 olduklarını (göre yukarıdan aşağıya sayarak) belirleyin. Her biri söz konusu sütun için DBSTATUS_S_OK döndürür. Diğer tüm sütunlar için DBSTATUS_S_ISNULL döndürür. Bir tüketici, dönüş değeri NULL veya başka bir şey olduğunu anlamayabilir çünkü bu durumuna döndürmek önemlidir. Yeniden NULL boş ile eşdeğer olduğunu unutmayın.  
  
 OLE DB şema satır kümesi arabirimi hakkında daha fazla bilgi için bkz. [IDBSchemaRowset](../../data/oledb/idbschemarowsetimpl-class.md) arabirimi OLE DB Programcı Başvurusu.  
  
 Tüketiciler nasıl kullanabileceğiniz hakkında bilgi için `IDBSchemaRowset` yöntemleri bkz [kümelerinin şema satır kümeleri ile](../../data/oledb/obtaining-metadata-with-schema-rowsets.md).  
  
 Şema satır kümeleri destekleyen bir sağlayıcı örneği için bkz: [UpdatePV](http://msdn.microsoft.com/c8bed873-223c-4a7d-af55-f90138c6f38f) örnek.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gelişmiş Sağlayıcı Teknikleri](../../data/oledb/advanced-provider-techniques.md)