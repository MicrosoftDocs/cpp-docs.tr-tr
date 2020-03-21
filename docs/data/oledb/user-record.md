---
title: Kullanıcı Kaydı
ms.date: 05/09/2019
helpviewer_keywords:
- records, user
- OLE DB providers, user record
- user records
- user records, described
- rowsets, user record
ms.assetid: 9c0d2864-2738-4f62-a750-1016d9c3523f
ms.openlocfilehash: 4a8fb6c9eeee3736501a04a095bdd763de16de7d
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078997"
---
# <a name="user-record"></a>Kullanıcı Kaydı

> [!NOTE]
> ATL OLE DB sağlayıcı Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz.

Kullanıcı kaydı, bir satır kümesi için sütun verilerini temsil eden kodu ve veri yapısını sağlar. Bir kullanıcı kaydı, derleme zamanında veya çalışma zamanında oluşturulabilir. **ATL OLE DB sağlayıcı Sihirbazı 'nı**kullanarak bir sağlayıcı oluşturduğunuzda, sihirbaz şuna benzer bir varsayılan kullanıcı kaydı oluşturur ( *bir sağlayıcı adı*[kısa ad] belirtmediğiniz varsayılarak):

```cpp
class CWindowsFile:
   public WIN32_FIND_DATA
{
public:
  
BEGIN_PROVIDER_COLUMN_MAP(CMyProviderWindowsFile)
   PROVIDER_COLUMN_ENTRY("FileAttributes", 1, dwFileAttributes)
   PROVIDER_COLUMN_ENTRY("FileSizeHigh", 2, nFileSizeHigh)
   PROVIDER_COLUMN_ENTRY("FileSizeLow", 3, nFileSizeLow)
   PROVIDER_COLUMN_ENTRY_STR("FileName", 4, cFileName)
   PROVIDER_COLUMN_ENTRY_STR("AltFileName", 5, cAlternateFileName)
END_PROVIDER_COLUMN_MAP()
  
};
```

OLE DB sağlayıcı şablonları, istemciyle etkileşimlerle ilgili tüm OLE DB özellikleri işler. Bir yanıt için gereken sütun verisini almak için sağlayıcı, kullanıcı kaydına yerleştirmeniz gereken `GetColumnInfo` işlevini çağırır. Kullanıcı kaydındaki `GetColumnInfo`, örneğin, burada gösterildiği gibi. h dosyasında bildirerek açıkça geçersiz kılabilirsiniz:

```cpp
template <class T>
static ATLCOLUMNINFO* GetColumnInfo(T* pThis, ULONG* pcCols)
```

Bu, şu şekilde yapılır:

```cpp
static ATLCOLUMNINFO* GetColumnInfo(CommandClass* pThis, ULONG* pcCols)
static ATLCOLUMNINFO* GetColumnInfo(RowsetClass* pThis, ULONG* pcCols)
```

Ardından, Kullanıcı kaydının. cpp dosyasında `GetColumnInfo` uygulayın.

PROVIDER_COLUMN_MAP makroları `GetColumnInfo` işlevi oluşturmaya yardımcı olur:

- BEGIN_PROVIDER_COLUMN_MAP, işlev prototipini ve statik bir `ATLCOLUMNINFO` yapıları dizisini tanımlar.

- PROVIDER_COLUMN_ENTRY tek bir `ATLCOLUMNINFO`tanımlar ve başlatır.

- END_PROVIDER_COLUMN_MAP diziyi ve işlevi kapatır. Ayrıca, dizi öğe sayısını *pcCols* parametresine koyar.

Çalışma zamanında bir kullanıcı kaydı oluşturulduğunda `GetColumnInfo`, bir satır kümesine veya komut örneğine bir işaretçi almak için *pThis* parametresini kullanır. Komutların ve satır kümelerinin `IColumnsInfo` arabirimini desteklemesi gerekir, bu nedenle sütun bilgileri bu işaretçiden alınabilir.

`CommandClass` ve `RowsetClass`, Kullanıcı kaydını kullanan komut ve satır kümesidir.

Bir Kullanıcı kaydındaki `GetColumnInfo` geçersiz kılma hakkında daha ayrıntılı bir örnek için bkz. [tüketiciye döndürülen sütunları dinamik olarak belirleme](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
