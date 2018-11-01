---
title: Kullanıcı Kayıtları
ms.date: 10/22/2018
f1_keywords:
- COLUMN_ENTRY_MAP
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
ms.openlocfilehash: 4d52c36368b9b39815cbb9a103f84f140626ba2b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50567446"
---
# <a name="user-records"></a>Kullanıcı Kayıtları

Statik erişimci kullanılacak (dan türetilen bir erişimci `CAccessor`), bir kullanıcı kaydı tüketiciye sahip olmanız gerekir. Kullanıcı tanıtıcı giriş veya çıkış için veri öğeleri içeren bir C++ sınıfı kaydıdır. **ATL OLE DB Tüketicisi Sihirbazı** , tüketici için bir kullanıcı kaydı oluşturur. Kullanıcı kaydı komutları işleme gibi isteğe bağlı görevler için yöntemler ekleyebilirsiniz.

Aşağıdaki kod, komutları işleyen bir örneği kayıt gösterir. Kullanıcı kaydında BEGIN_COLUMN_MAP tüketiciye sağlayıcıdan geçen veri satır kümesini temsil eder. BEGIN_PARAM_MAP komut parametreleri kümesini temsil eder. Bu örnekte bir [CCommand](../../data/oledb/ccommand-class.md) komut parametreleri işlemek için sınıf. Eşleme girişleri veri üyeleri, bitişik bir sınıfın her örneği için bellek bloğu içine uzaklıkları temsil eder. COLUMN_ENTRY makroları PROVIDER_COLUMN_ENTRY sağlayıcı tarafındaki karşılık gelir.

COLUMN_MAP ve PARAM_MAP makrolar hakkında daha fazla bilgi için bkz. [OLE DB Tüketici Şablonları için makrolar](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md).

```cpp
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

## <a name="wizard-generated-user-records"></a>Sihirbaz tarafından oluşturulan kullanıcı kaydı

Kullanırsanız **ATL OLE DB Tüketicisi Sihirbazı** tüketici oluşturmak için OLE DB Şablonları veya OLE DB öznitelikleri kullanma seçeneğiniz vardır. Oluşturulan kod, her durumda farklıdır. Bu kod hakkında daha fazla bilgi için bkz: [kodla](../../data/oledb/consumer-wizard-generated-classes.md).

## <a name="user-record-support-for-multiple-accessors"></a>Çoklu erişimci için kullanıcı kayıt desteği

Gerektiği çoklu erişimci kullanılacak senaryolarda ayrıntılı bir açıklaması için [üzerinde bir satır kümesinde çoklu erişimci kullanarak](../../data/oledb/using-multiple-accessors-on-a-rowset.md).

Aşağıdaki örnek, kullanıcı kayıt satır kümesinde çoklu erişimci desteklemek için değiştirildi gösterir. BEGIN_COLUMN_MAP ve END_COLUMN_MAP yerine kullandığı [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md) ve [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) her erişimcisi için. BEGIN_ACCESSOR makrosu erişimcisi sayısını (sıfır sapma) ve erişimcisi erişimcinin olup olmadığını belirtir. Erişimciler `GetData` verileri otomatik olarak bir çağrı almak için [MoveNext](../../data/oledb/crowset-movenext.md). Otomatik olmayan erişimciler açıkça verileri almanızı gerektirir. Otomatik olmayan bir erişimci almak için her kayıt için isteyebileceğiniz değil bir büyük veri alanına (örneğin, bit eşlem görüntüsüne) bağlanıyorsa bu değeri kullanın.

```cpp
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