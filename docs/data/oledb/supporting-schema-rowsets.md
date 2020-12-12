---
description: 'Daha fazla bilgi edinin: şema satır kümelerini destekleme'
title: Şema Satır Kümelerini Destekleme
ms.date: 11/04/2016
helpviewer_keywords:
- schema rowsets
- OLE DB consumer templates, schema rowsets
- OLE DB providers, schema rowsets
- OLE DB, schema rowsets
ms.assetid: 71c5e14b-6e33-4502-a2d9-a1dc6d6e9ba0
ms.openlocfilehash: 029b05f594dda01112cd975543462f92e351b1c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272740"
---
# <a name="supporting-schema-rowsets"></a>Şema Satır Kümelerini Destekleme

Şema satır kümeleri, tüketicilerin temel yapısını veya şemayı bilmeden bir veri deposu hakkında bilgi almasını sağlar. Örneğin, bir veri deposunda tablolar Kullanıcı tanımlı bir hiyerarşide düzenlenmiş olabilir. bu nedenle, onu okuyarak şema hakkında bilgi sağlamaya yönelik bir yol yoktur. (Başka bir örnek olarak, Visual C++ sihirbazları tüketici için erişimcileri oluşturmak üzere şema satır kümelerini kullanır.) Tüketicinin bunu yapmasına izin vermek için, sağlayıcının oturum nesnesi [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) arabirimindeki yöntemleri kullanıma sunar. Visual C++ uygulamalarda, uygulamak için [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) sınıfını kullanırsınız `IDBSchemaRowset` .

`IDBSchemaRowsetImpl` Aşağıdaki yöntemleri destekler:

- [CheckRestrictions](./idbschemarowsetimpl-class.md#checkrestrictions) , bir şema satır kümesi için kısıtlamaların geçerliliğini denetler.

- [CreateSchemaRowset](./idbschemarowsetimpl-class.md#createschemarowset) , şablon parametresi tarafından belirtilen nesne IÇIN bir com nesnesi Oluşturucu işlevi uygular.

- [SetRestrictions](./idbschemarowsetimpl-class.md#setrestrictions) , belirli bir şema satır kümesinde hangi kısıtlamaları destekliyoruz belirtir.

- [IDBSchemaRowset:: GetRowset](./idbschemarowsetimpl-class.md#getrowset) bir şema satır kümesi (arabiriminden devralınmış) döndürüyor.

- [GetSchemas](./idbschemarowsetimpl-class.md#getschemas) , tarafından erişilebilen `IDBSchemaRowsetImpl::GetRowset` (arabiriminden devralınan) şema satır kümelerinin bir listesini döndürür.

## <a name="atl-ole-db-provider-wizard-support"></a>ATL OLE DB sağlayıcı Sihirbazı desteği

::: moniker range="msvc-160"

ATL OLE DB sağlayıcı Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz.

::: moniker-end

::: moniker range="<=msvc-150"

**ATL OLE DB sağlayıcı Sihirbazı** , oturum üstbilgi dosyasında üç şema sınıfı oluşturur:

- **C**<em>ShortName</em>**SessionTRSchemaRowset**

- **C**<em>ShortName</em>**SessionColSchemaRowset**

- **C**<em>ShortName</em>**SessionPTSchemaRowset**

Bu sınıflar, şema bilgileri için tüketici isteklerine yanıt verir; OLE DB belirtiminin bu üç şema satır kümelerinin desteklendiğini unutmayın:

- **C**<em>ShortName</em>**SessionTRSchemaRowset** , tablo bilgileri için istekleri işler (DBSCHEMA_TABLES şeması satır kümesi).

- **C**<em>ShortName</em>**SessionColSchemaRowset** , sütun bilgileri için istekleri işler (DBSCHEMA_COLUMNS şeması satır kümesi). Sihirbaz, bu sınıflar için bir DOS sağlayıcısı için şema bilgilerini döndüren örnek uygulamalar sağlar.

- **C**<em>ShortName</em>**SessionPTSchemaRowset** , sağlayıcı türü (DBSCHEMA_PROVIDER_TYPES şeması satır kümesi) hakkındaki şema bilgileri için istekleri işler. Sihirbaz tarafından belirtilen varsayılan uygulama S_OK döndürür.

Bu sınıfları, sağlayıcınıza uygun şema bilgilerini işleyecek şekilde özelleştirebilirsiniz:

- **C**<em>ShortName</em>**SessionTRSchemaRowset** içinde, katalog, tablo ve Açıklama alanlarını ( `trData.m_szType` , `trData.m_szTable` ve) doldurmanız gerekir `trData.m_szDesc` . Sihirbaz tarafından oluşturulan örnek yalnızca bir satır (tablo) kullanır. Diğer sağlayıcılar birden fazla tablo döndürebilir.

- **C**<em>ShortName</em>**SessionColSchemaRowset** içinde, tablonun adını olarak geçirirsiniz `DBID` .

::: moniker-end

## <a name="setting-restrictions"></a>Kısıtlama ayarlama

Şema satır kümesi desteğiyle önemli bir kavram, kullanmakta olduğunuz ayar kısıtlamalardır `SetRestrictions` . Kısıtlamalar tüketicilere yalnızca eşleşen satırları getirme izni verir (örneğin, "MyTable" tablosundaki tüm sütunları bulur). Kısıtlamalar isteğe bağlıdır ve hiçbirinin desteklenme durumunda (varsayılan), tüm veriler her zaman döndürülür. Kısıtlamaları destekleyen bir sağlayıcıya örnek için bkz. [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) örneği.

## <a name="setting-up-the-schema-map"></a>Şema haritasını ayarlama

UpdatePV içindeki session. h içinde bu gibi bir şema eşlemesi ayarlayın:

```cpp
BEGIN_SCHEMA_MAP(CUpdateSession)
    SCHEMA_ENTRY(DBSCHEMA_TABLES, CUpdateSessionTRSchemaRowset)
    SCHEMA_ENTRY(DBSCHEMA_COLUMNS, CUpdateSessionColSchemaRowset)
    SCHEMA_ENTRY(DBSCHEMA_PROVIDER_TYPES, CUpdateSessionPTSchemaRowset)
END_SCHEMA_MAP()
```

' Yi desteklemek için `IDBSchemaRowset` DBSCHEMA_TABLES, DBSCHEMA_COLUMNS ve DBSCHEMA_PROVIDER_TYPES desteklemeniz gerekir. Daha uygun şema satır kümeleri ekleyebilirsiniz.

İçindeki gibi bir yöntemle şema satır kümesi sınıfı bildirin `Execute` `CUpdateSessionTRSchemaRowset` `UpdatePV` :

```cpp
class CUpdateSessionTRSchemaRowset :
    public CSchemaRowsetImpl < CUpdateSessionTRSchemaRowset,
                              CTABLESRow, CUpdateSession >
...
// Execute looks like this; what pointers does the consumer use?
    HRESULT Execute(DBROWCOUNT* pcRowsAffected,
                    ULONG cRestrictions, const VARIANT* rgRestrictions)
```

`CUpdateSession` öğesinden devraldığından `IDBSchemaRowsetImpl` tüm kısıtlama işleme yöntemlerine sahiptir. Kullanarak `CSchemaRowsetImpl` üç alt sınıf bildirin (yukarıdaki şema haritasında listelenmiştir): `CUpdateSessionTRSchemaRowset` , `CUpdateSessionColSchemaRowset` , ve `CUpdateSessionPTSchemaRowset` . Bu alt sınıfların her birinde `Execute` ilgili kısıtlama kümesini (arama ölçütü) işleyen bir yöntemi vardır. Her `Execute` Yöntem, *CRestrictions* ve *rgRestrictions* parametrelerinin değerlerini karşılaştırır. [SetRestrictions](./idbschemarowsetimpl-class.md#setrestrictions)içindeki bu parametrelerin açıklamasına bakın.

Belirli bir şema satır kümesine karşılık gelen kısıtlamalar hakkında daha fazla bilgi için, Windows SDK **OLE DB Programcı başvurusu** Içindeki [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) Içindeki şema satır kümesi GUID 'lerinin tablosuna bakın.

Örneğin, DBSCHEMA_TABLES TABLE_NAME kısıtlamasını destekleniyorsa, şunları yapabilirsiniz:

İlk olarak, DBSCHEMA_TABLES araması yapın ve dört kısıtlamayı (sırasıyla) desteklediğini öğrenin.

|Şema satır kümesi kısıtlaması|Kısıtlama değeri|
|-------------------------------|-----------------------|
|TABLE_CATALOG|0x1 (ikili 1)|
|TABLE_SCHEMA|0x2 (ikili 10)|
|TABLE_NAME|0x4 (ikili 100)|
|TABLE_TYPE|0x8 (ikili 1000)|

Ardından, her kısıtlama için bir bit vardır. Yalnızca TABLE_NAME desteklemek istiyorsanız, öğesinde 0x4 döndürün `rgRestrictions` . TABLE_CATALOG ve TABLE_NAME destekleniyorsa, 0x5 (ikili 101) döndürün.

Varsayılan olarak, uygulama herhangi bir istek için 0 (herhangi bir kısıtlamayı desteklemez) değerini döndürür. UpdatePV, kısıtlamaları destekleyen bir sağlayıcıya örnektir.

### <a name="example"></a>Örnek

Bu kod, [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) örneğinden alınır. `UpdatePv` gerekli üç şema satır kümelerini destekler: DBSCHEMA_TABLES, DBSCHEMA_COLUMNS ve DBSCHEMA_PROVIDER_TYPES. Bu konu, Sağlayıcınızda şema desteğinin nasıl uygulanacağı hakkında bir örnek olarak, DBSCHEMA_TABLE satır kümesini uygularken size kılavuzluk ediyor.

> [!NOTE]
> Örnek kod, burada listelenenden farklı bir durum içerebilir; örnek kodu daha güncel sürüme göre görmeniz gerekir.

Şema desteği eklemenin ilk adımı hangi kısıtlamaları destekleyeceksiniz. Şema satır kümesinde hangi kısıtlamaların kullanılabildiğini öğrenmek için, tanımı için OLE DB belirtimine bakın `IDBSchemaRowset` . Ana tanımı izleyerek şema satır kümesi adını, kısıtlama sayısını ve kısıtlama sütunlarını tutan bir tablo görürsünüz. Desteklemek istediğiniz şema satır kümesini seçin ve kısıtlama ve kısıtlama sütunlarının sayısını göz önünde yapın. Örneğin, DBSCHEMA_TABLES dört kısıtlamayı destekler (TABLE_CATALOG, TABLE_SCHEMA, TABLE_NAME ve TABLE_TYPE):

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

Bit her kısıtlama sütununu temsil eder. Bir kısıtlamayı desteklemek istiyorsanız (diğer bir deyişle, bunu sorgulayabilirsiniz), bu biti bir 1 olarak ayarlayın. Bir kısıtlamayı desteklemek istemiyorsanız, bu biti sıfır olarak ayarlayın. Yukarıdaki kod satırından, `UpdatePV` DBSCHEMA_TABLES satır kümesinde table_name ve TABLE_TYPE kısıtlamalarını destekler. Bunlar üçüncü (bit maskesi 100) ve dördüncü (bit maskesi 1000) kısıtlamalardır. Bu nedenle, için bit maskesi `UpdatePv` 1100 (veya 0x0C) olur:

```cpp
if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_TABLES))
    rgRestrictions[l] = 0x0C;
```

Aşağıdaki `Execute` işlev normal satır kümelerinde benzerdir. Üç bağımsız değişkendir: *Pcrowsabetkilenen*, *CRestrictions* ve *rgRestrictions*. *Pcrowsaetkilenen* değişkeni, sağlayıcının şema satır kümesinde satır sayısını döndüre, bir çıkış parametresidir. *CRestrictions* parametresi, tüketici tarafından Sağlayıcıya geçirilen kısıtlamaların sayısını tutan bir giriş parametresidir. *RgRestrictions* parametresi, kısıtlama değerlerini tutan bir değişken değerleri dizisidir.

```cpp
HRESULT Execute(DBROWCOUNT* pcRowsAffected, ULONG cRestrictions,
                const VARIANT* rgRestrictions)
```

*CRestrictions* değişkeni, sağlayıcının desteklemesinden bağımsız olarak, bir şema satır kümesi için toplam kısıtlama sayısını temel alır. UpdatePv iki kısıtlamayı (üçüncü ve dördüncü) desteklediğinden, bu kod yalnızca üçten büyük veya buna eşit bir *CRestrictions* değeri arar.

TABLE_NAME kısıtlamasının değeri *rgRestrictions [2]* içinde depolanır (yeniden sıfır tabanlı dizide üçüncü kısıtlama 2 ' dir). Kısıtlamanın gerçekten desteklemek için VT_EMPTY olup olmadığını kontrol edin. VT_NULL VT_EMPTY eşit olmadığını unutmayın. VT_NULL geçerli bir kısıtlama değeri belirtiyor.

`UpdatePv`Tablo adının tanımı, bir metin dosyasının tam yolu adıdır. Kısıtlama değerini ayıklayın ve dosyanın gerçekten mevcut olduğundan emin olmak için dosyayı açmayı deneyin. Dosya yoksa, S_OK döndürün. Bu, geriye doğru görünebilir, ancak müşterinin belirtilen ada göre desteklenen tablo olmadığını belirten kodun gerçekten anlamı vardır. S_OK dönüş, kodun doğru şekilde yürütüldüğü anlamına gelir.

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

Dördüncü kısıtlamayı (TABLE_TYPE) destekleme, üçüncü kısıtlamaya benzerdir. Değerin VT_EMPTY olup olmadığını denetleyin. Bu kısıtlama yalnızca tablo türü, tablo döndürür. DBSCHEMA_TABLES geçerli değerlerini öğrenmek için tablolar satır kümesi bölümünde **OLE DB Programcı başvurusunun** **Ek B** bölümüne bakın.

```cpp
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

Aslında satır kümesi için bir satır girişi oluşturduğunuz yerdir. Değişkeni `trData` `CTABLESRow` , OLE DB sağlayıcısı şablonlarında tanımlanan bir yapıya karşılık gelir. `CTABLESRow` OLE DB belirtiminin **Ek B** içindeki tablolar satır kümesi tanımına karşılık gelir. Yalnızca bir tabloyu tek seferde destekleyebilmeniz için yalnızca bir satırınız vardır.

```cpp
// Bring over the data:
wcspy_s(trData.m_szType, OLESTR("TABLE"), 5);

wcspy_s(trData.m_szDesc, OLESTR("The Directory Table"), 19);

wcsncpy_s(trData.m_szTable, T2OLE(szFile), _TRUNCATE());
```

`UpdatePV` yalnızca üç sütun ayarlar: TABLE_NAME, TABLE_TYPE ve açıklama. Şunları uygularken bu bilgilere ihtiyacınız olduğundan, bilgilerini geri döndürdüğüne ilişkin sütunları bir yere unutmayın `GetDBStatus` :

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

`GetDBStatus`İşlevi, şema satır kümesi için doğru işlem açısından önemlidir. TABLOLAR satır kümesindeki her sütun için veri döndürmediğinden, veri döndürmeniz gereken sütunları belirtmeniz ve hangilerinin istemediğiniz sütunları belirtmeniz gerekir.

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

`Execute`İşleviniz tablolar satır kümesinden table_name, TABLE_TYPE ve açıklama alanları için veri döndürdüğünden, OLE DB belirtiminin **Ek B** bölümüne bakabilir ve (yukarıdan aşağı doğru sayarak) 3, 4 ve 6 sıra sayısını belirleyebilirsiniz. Bu sütunların her biri için DBSTATUS_S_OK döndürün. Diğer tüm sütunlar için DBSTATUS_S_ISNULL döndürün. Bu durumun döndürülmesi önemlidir çünkü bir tüketici, döndürüleyi döndürülen değerin NULL ya da başka bir şey olduğunu anlamayabilir. Yine, NULL değeri boş değer olmadığını unutmayın.

OLE DB şeması satır kümesi arabirimi hakkında daha fazla bilgi için, **OLE DB Programcı başvurusunda** [IDBSchemaRowset](../../data/oledb/idbschemarowsetimpl-class.md) arabirimine bakın.

Tüketicilerin yöntemleri nasıl kullanabileceği hakkında daha fazla bilgi için `IDBSchemaRowset` bkz. [şema satır kümeleri Ile meta veri alma](../../data/oledb/obtaining-metadata-with-schema-rowsets.md).

Şema satır kümelerini destekleyen bir sağlayıcıya örnek için bkz. [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) örneği.

## <a name="see-also"></a>Ayrıca bkz.

[Gelişmiş sağlayıcı teknikleri](../../data/oledb/advanced-provider-techniques.md)
