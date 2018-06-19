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
ms.openlocfilehash: 95f1455fde75ec835486cbcc3d590822891d14f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33111763"
---
# <a name="supporting-schema-rowsets"></a>Şema Satır Kümelerini Destekleme
Şema satır kümeleri kendi yapılarını veya şema bilmeden bir veri deposu hakkında bilgi edinmek tüketicilere izin verir. Örneğin, bir veri deposu olurdu şekilde okuma tarafından şemanın bilgi sağlamak için hiçbir şekilde bir kullanıcı tarafından tanımlanan hiyerarşide düzenlenmiş tablolar olabilir. (Başka bir örnek olarak, Visual C++ sihirbazları tüketici erişimcileri oluşturmak için şema satır kümeleri kullandığını unutmayın.) Bunu yapmak izin vermek üzere üzerinde yöntemlerini sağlayıcının oturum nesnesi gösterir [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) arabirimi. Visual C++ uygulamalarında kullandığınız [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) uygulamak için sınıf **IDBSchemaRowset**.  
  
 `IDBSchemaRowsetImpl` Aşağıdaki yöntemlerden destekler:  
  
-   [CheckRestrictions](../../data/oledb/idbschemarowsetimpl-checkrestrictions.md) bir şema satır kümesi karşı kısıtlamaların geçerliliğini denetler.  
  
-   [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md) şablon parametresi tarafından belirtilen nesne için bir COM nesnesi oluşturucu işlevi uygular.  
  
-   [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md) belirli şema satır kümesinde desteklediğiniz hangi kısıtlamaları belirtir.  
  
-   [IDBSchemaRowset::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md) (arabiriminden devralınmış) bir şema satır kümesi döndürür.  
  
-   [GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md) şema satır kümeleri tarafından erişilebilen döndürür `IDBSchemaRowsetImpl::GetRowset` (arabiriminden devralınmış).  
  
## <a name="atl-ole-db-provider-wizard-support"></a>ATL OLE DB Sağlayıcı Sihirbazı desteği  
 ATL OLE DB Sağlayıcı Sihirbazı oturum üstbilgi dosyasında üç şema sınıfları oluşturur:  
  
-   **C** *kısaad* **SessionTRSchemaRowset**  
  
-   **C** *kısaad* **SessionColSchemaRowset**  
  
-   **C** *kısaad* **SessionPTSchemaRowset**  
  
 Bu sınıfları, şema bilgileri tüketici isteklere yanıt verir; OLE DB belirtiminin bu üç şema satır kümeleri desteklenmesi gerektirdiğini unutmayın:  
  
-   **C** *kısaad* **SessionTRSchemaRowset** tablo bilgilerine yönelik istekleri işleyen ( `DBSCHEMA_TABLES` şeması satır kümesi).  
  
-   **C** *kısaad* **SessionColSchemaRowset** sütun bilgisi isteklerini işleme ( **DBSCHEMA_COLUMNS** şeması satır kümesi). Sihirbazın bu sınıfların DOS sağlayıcı için şema bilgileri döndürmek için örnek uygulamaları sağlar.  
  
-   **C** *kısaad* **SessionPTSchemaRowset** sağlayıcı türü hakkındaki şema bilgilerine yönelik istekleri işleyen ( **DBSCHEMA_PROVIDER_TYPES** şeması satır kümesi). Sihirbaz tarafından sağlanan varsayılan uygulama döndürür `S_OK`.  
  
 Sağlayıcınıza uygun şema bilgileri işlemek için bu sınıfların özelleştirebilirsiniz:  
  
-   İçinde **C***kısaad***SessionTRSchemaRowset**, katalog, tablo ve açıklama alanları doldurun gerekir (**trData.m_szType**, **trData.m_szTable** , ve **trData.m_szDesc**). Sihirbaz tarafından oluşturulan örnek, yalnızca bir satır (tablo) kullanır. Diğer sağlayıcıları birden fazla tablo döndürebilir.  
  
-   İçinde **C***kısaad***SessionColSchemaRowset**, tablo olarak adını geçirmek bir **DBID**.  
  
## <a name="setting-restrictions"></a>Kısıtlamalarını ayarlama  
 Şema satır kümesi desteği de önemli bir kavram kullanarak bunu kısıtlamaları ayarı `SetRestrictions`. Kısıtlamalar yalnızca eşleşen satırları getirmeye tüketicileri izin ver (örneğin, tüm sütunlara "MyTable" tablosunda Bul). Kısıtlamaları isteğe bağlıdır ve durumda hiçbirinin desteklenir (varsayılan), tüm veriler her zaman döndürülür. Kısıtlamaları destekleyen bir sağlayıcı örneği için bkz: [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f) örnek.  
  
## <a name="setting-up-the-schema-map"></a>Şema eşleme ayarlama  
 Şema eşleme UpdatePV Session.h'deki bunun gibi ayarlayın:  
  
```  
BEGIN_SCHEMA_MAP(CUpdateSession)  
    SCHEMA_ENTRY(DBSCHEMA_TABLES, CUpdateSessionTRSchemaRowset)  
    SCHEMA_ENTRY(DBSCHEMA_COLUMNS, CUpdateSessionColSchemaRowset)  
    SCHEMA_ENTRY(DBSCHEMA_PROVIDER_TYPES, CUpdateSessionPTSchemaRowset)  
END_SCHEMA_MAP()  
```  
  
 Desteklemek için **IDBSchemaRowset**, desteklemeniz gereken `DBSCHEMA_TABLES`, **DBSCHEMA_COLUMNS**, ve **DBSCHEMA_PROVIDER_TYPES**. Ek şema satır kümeleri ekleyebilirsiniz.  
  
 Bir şema satır kümesi sınıfla bildirme bir `Execute` yöntemi gibi `CUpdateSessionTRSchemaRowset` UpdatePV:  
  
```  
class CUpdateSessionTRSchemaRowset :   
    public CSchemaRowsetImpl < CUpdateSessionTRSchemaRowset,   
                              CTABLESRow, CUpdateSession >  
...  
// Execute looks like this; what pointers does the consumer use?  
    HRESULT Execute(DBROWCOUNT* pcRowsAffected,   
                    ULONG cRestrictions, const VARIANT* rgRestrictions)  
```  
  
 Unutmayın `CUpdateSession` devraldığı `IDBSchemaRowsetImpl`, tüm kısıtlama yöntemleri işleme sahiptir. Kullanarak `CSchemaRowsetImpl`, üç alt sınıflar (şema eşlemede listelenir) bildirin: `CUpdateSessionTRSchemaRowset`, `CUpdateSessionColSchemaRowset`, ve `CUpdateSessionPTSchemaRowset`. Bu alt sınıfların her biri olan bir `Execute` kendi kendine kısıtlama (arama ölçütleri) işleyen yöntem. Her `Execute` yöntemi değerlerini karşılaştırır `cRestrictions` ve `rgRestrictions` parametreleri. Bu parametreler açıklamasına bakın [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md).  
  
 Kısıtlamaları hakkında belirli şeması satır kümesi için karşılık daha fazla bilgi için şema satır kümesi GUID'ler tablosunun başvurun içinde [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) içinde *OLE DB Programcının Başvurusu* içinde Windows SDK.  
  
 Örneğin, desteklenen **TABLE_NAME** ilgili bir kısıtlama `DBSCHEMA_TABLES`, aşağıdakileri yapmanız gerekir:  
  
 İlk olarak, arama `DBSCHEMA_TABLES` ve dört kısıtlamaları (sırayla) destekler.  
  
|Şema satır kümesi kısıtlama|Kısıtlama değeri|  
|-------------------------------|-----------------------|  
|**TABLE_CATALOG**|0x1 (ikili 1)|  
|**TABLE_SCHEMA**|0x2 (ikili 10)|  
|**TABLE_NAME**|0x4 (ikili 100)|  
|**TABLE_TYPE**|0x8 (ikili 1000)|  
  
 Ardından, her kısıtlama için bir bit olduğuna dikkat edin. Desteklemek istediğiniz çünkü **TABLE_NAME** yalnızca 0x4 geri `rgRestrictions` öğesi. Desteklenen varsa **TABLE_CATALOG** ve **TABLE_NAME**, 0x5 (binary 101) döndürecektir.  
  
 Varsayılan olarak, uygulama herhangi bir istek için 0 (herhangi bir kısıtlama desteklemez) döndürür. UpdatePV kısıtlamaları destekleyen bir sağlayıcı örneğidir.  
  
### <a name="example"></a>Örnek  
 Bu kod alınırlar [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f) örnek. UpdatePv üç gerekli şema satır kümeleri destekler: `DBSCHEMA_TABLES`, **DBSCHEMA_COLUMNS**, ve **DBSCHEMA_PROVIDER_TYPES**. Uygulama üzerinden nasıl şema desteği sağlayıcınızda uygulayacağınıza dair örnek olarak, bu konuda, geçen **DBSCHEMA_TABLE** satır kümesi.  
  
> [!NOTE]
>  Örnek kod, ne burada listelenen alanından farklı olabilir; Örnek kod daha güncel bir sürüm olarak göz önüne almalısınız.  
  
 Şema desteği ekleme ilk adımı, hangi kısıtlamaları desteklemek için destekleyeceğinizi belirlemektir. Hangi kısıtlamaları şema satır kümesi için kullanılabilir olduğunu belirlemek üzere tanımı için OLE DB belirtimine bakın **IDBSchemaRowset**. Ana tanımı, şema satır kümesi adı, kısıtlama sayısı ve kısıtlama sütunları içeren bir tabloya bakın. Kısıtlamaları ve kısıtlama sütun sayısını not edin ve desteklemek için istediğiniz şeması satır kümesi seçin. Örneğin, `DBSCHEMA_TABLES` dört kısıtlamayı destekler (**TABLE_CATALOG**, **TABLE_SCHEMA**, **TABLE_NAME**, ve **TABLE_TYPE** ):  
  
```  
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
  
 Bir bit her kısıtlama sütunu temsil eder. Bir kısıtlama desteklemek istiyorsanız (diğer bir deyişle, sorgulayabilirsiniz), o biti 1 olarak ayarlayın. Bir kısıtlama desteklemek istemiyorsanız bu bit sıfır olarak ayarlayın. Yukarıdaki kod satırından UpdatePV destekleyen **TABLE_NAME** ve **TABLE_TYPE** kısıtlamalar `DBSCHEMA_TABLES` satır kümesi. (Bit maskesi: 100) üçüncü ve dördüncü (bit maskesi 1000) kısıtlamaları bunlar. Bu nedenle, UpdatePv için bit maskesi 1100 (veya 0x0C) verilmiştir:  
  
```  
if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_TABLES))  
    rgRestrictions[l] = 0x0C;  
```  
  
 Aşağıdaki `Execute` işlevi normal satır kümeleri benzer. Üç bağımsız değişkeni vardır: `pcRowsAffected`, `cRestrictions`, ve `rgRestrictions`. `pcRowsAffected` Değişkeni, bir output parametresi sağlayıcı şeması satır kümesi satırların sayımını geri dönebilirsiniz. `cRestrictions` Tüketici tarafından sağlayıcıya geçirilen kısıtlamaların sayısını içeren bir parametredir giriş. `rgRestrictions` Parametredir bir dizi **değişken** kısıtlama değerleri içeren bir değerler.  
  
```  
HRESULT Execute(DBROWCOUNT* pcRowsAffected, ULONG cRestrictions,   
                const VARIANT* rgRestrictions)  
```  
  
 `cRestrictions` Değişkeni sağlayıcı bunları destekleyip desteklemediğini bakılmaksızın bir şema satır kümesi için kısıtlamalar toplam sayısını temel alır. UpdatePv iki kısıtlama (üçüncü ve dördüncü) desteklediği için bu kod yalnızca arar bir `cRestrictions` üç eşit veya daha büyük bir değer.  
  
 Değeri **TABLE_NAME** kısıtlama depolanır `rgRestrictions[2]` (yeniden sıfır tabanlı bir dizi üçüncü kısıtlamada 2'dir). Kısıtlama olmadığını kontrol etmeniz `VT_EMPTY` gerçekten desteklemek için. Unutmayın **VT_NULL** eşit değil `VT_EMPTY`. **VT_NULL** geçerli bir kısıtlama değeri belirtir.  
  
 Bir metin dosyasına tam yol adı bir tablo adının UpdatePv tanımıdır. Kısıtlama değerini ayıklayın ve dosyanın gerçekten var olmadığından emin olmak için dosyayı açmayı deneyin. Dosya mevcut değilse dönmek `S_OK`. Bu biraz geriye doğru görünebilir ancak hangi kodu gerçekten tüketici söyleyen belirtilen ad tarafından desteklenen hiçbir tablo olduğunu değildir. `S_OK` Return anlamına doğru yürütülen kod.  
  
```  
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
  
 Dördüncü kısıtlama destekleme (**TABLE_TYPE**) üçüncü kısıtlamaya benzerdir. Değerin olmadığını görmek için onay `VT_EMPTY`. Bu kısıtlama yalnızca tablo türü döndürür **tablo**. İçin geçerli değerleri belirlemek için `DBSCHEMA_TABLES`, ek b'de Ara *OLE DB Programcının Başvurusu* içinde **tabloları** satır kümesi bölümü.  
  
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
  
 Satır kümesi için bir satır girişini gerçekte oluşturduğunuz budur. Değişkeni `trData` karşılık gelen **CTABLESRow**, OLE DB sağlayıcı şablonları içinde tanımlanmış bir yapı. **CTABLESRow** karşılık gelen **tabloları** ek B satır kümesi tanımında OLE DB belirtimi. Yalnızca aynı anda yalnızca bir tablo destekleyebilir çünkü eklemek için bir satır var.  
  
```  
// Bring over the data:  
wcspy_s(trData.m_szType, OLESTR("TABLE"), 5);  

wcspy_s(trData.m_szDesc, OLESTR("The Directory Table"), 19);  

wcsncpy_s(trData.m_szTable, T2OLE(szFile), _TRUNCATE());  
```  
  
 UpdatePV yalnızca üç sütun ayarlar: **TABLE_NAME**, **TABLE_TYPE**, ve **açıklama**. Gerçekleştirdiğinizde bu bilgiler gerektiğinden, bilgi, dönmek sütunları not edin `GetDBStatus`:  
  
```  
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
  
 `GetDBStatus` İşlevi şema satır kümesi doğru çalışması için çok önemlidir. Her sütun için veri döndürmeyen çünkü **tabloları** satır kümesi, hangi sütunların verilerini döndürür ve bunu yapmanız belirtmeniz gerekir.  
  
```  
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
  
 Çünkü, `Execute` işlevi için verileri döndürür **TABLE_NAME**, **TABLE_TYPE**, ve **açıklama** alanlarını **tabloları**satır kümesi, OLE DB belirtimine ek b'de arayın ve sıra numaraları 3, 4 ve 6 olduklarından emin (göre yukarıdan aşağıya sayarak) belirleyin. Bu sütunlardan her biri için dönüş **DBSTATUS_S_OK**. Tüm diğer sütunlar için iade **DBSTATUS_S_ISNULL**. Bir tüketici dönmek değer olduğunu anlamayabilir olduğundan dönüş bu durumu daha önemlidir **NULL** veya başka bir şey. Yeniden unutmayın **NULL** boş ile eşdeğer değil.  
  
 OLE DB şema satır kümesi arabirimi hakkında daha fazla bilgi için bkz: [IDBSchemaRowset](../../data/oledb/idbschemarowsetimpl-class.md) arabirimi OLE DB Programcı Başvurusu.  
  
 Tüketiciler nasıl kullanabileceğiniz hakkında bilgi için **IDBSchemaRowset** yöntemleri bkz [şema satır kümeleri ile meta veri alma](../../data/oledb/obtaining-metadata-with-schema-rowsets.md).  
  
 Şema satır kümeleri destekleyen bir sağlayıcı örneği için bkz: [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f) örnek.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gelişmiş Sağlayıcı Teknikleri](../../data/oledb/advanced-provider-techniques.md)