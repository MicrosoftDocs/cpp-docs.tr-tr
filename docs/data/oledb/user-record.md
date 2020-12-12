---
description: 'Daha fazla bilgi edinin: Kullanıcı kaydı'
title: Kullanıcı Kaydı
ms.date: 05/09/2019
helpviewer_keywords:
- records, user
- OLE DB providers, user record
- user records
- user records, described
- rowsets, user record
ms.assetid: 9c0d2864-2738-4f62-a750-1016d9c3523f
ms.openlocfilehash: f858660800391eff45cb88115f8fb09afa26a77f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272506"
---
# <a name="user-record"></a>Kullanıcı Kaydı

> [!NOTE]
> ATL OLE DB sağlayıcı Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz.

Kullanıcı kaydı, bir satır kümesi için sütun verilerini temsil eden kodu ve veri yapısını sağlar. Bir kullanıcı kaydı, derleme zamanında veya çalışma zamanında oluşturulabilir. **ATL OLE DB sağlayıcı Sihirbazı 'nı** kullanarak bir sağlayıcı oluşturduğunuzda, sihirbaz şuna benzer bir varsayılan kullanıcı kaydı oluşturur ( *bir sağlayıcı adı*[kısa ad] belirtmediğiniz varsayılarak):

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

OLE DB sağlayıcı şablonları, istemciyle etkileşimlerle ilgili tüm OLE DB özellikleri işler. Yanıt için gereken sütun verilerini almak için sağlayıcı, `GetColumnInfo` Kullanıcı kaydına yerleştirmeniz gereken işlevini çağırır. `GetColumnInfo`Kullanıcı kaydında, örneğin, burada gösterildiği gibi. h dosyasında bildirerek açıkça geçersiz kılabilirsiniz:

```cpp
template <class T>
static ATLCOLUMNINFO* GetColumnInfo(T* pThis, ULONG* pcCols)
```

Bu, şu şekilde yapılır:

```cpp
static ATLCOLUMNINFO* GetColumnInfo(CommandClass* pThis, ULONG* pcCols)
static ATLCOLUMNINFO* GetColumnInfo(RowsetClass* pThis, ULONG* pcCols)
```

Ardından, `GetColumnInfo` Kullanıcı kaydının. cpp dosyasına uygulayın.

PROVIDER_COLUMN_MAP makroları bir işlev oluşturmaya yardımcı olur `GetColumnInfo` :

- BEGIN_PROVIDER_COLUMN_MAP, işlev prototipini ve statik yapıların bir dizisini tanımlar `ATLCOLUMNINFO` .

- PROVIDER_COLUMN_ENTRY, tek bir tanımlar ve başlatır `ATLCOLUMNINFO` .

- END_PROVIDER_COLUMN_MAP diziyi ve işlevi kapatır. Ayrıca, dizi öğe sayısını *pcCols* parametresine koyar.

Çalışma zamanında bir kullanıcı kaydı oluşturulduğunda, bir `GetColumnInfo` satır kümesine veya komut örneğine bir işaretçi almak Için *pThis* parametresini kullanır. Komutların ve satır kümelerinin arabirimini desteklemesi gerekir `IColumnsInfo` , bu nedenle sütun bilgileri bu işaretçiden alınabilir.

`CommandClass` ve `RowsetClass` Kullanıcı kaydını kullanan komut ve satır kümesidir.

Kullanıcı kaydında nasıl geçersiz kılabileceğiniz hakkında daha ayrıntılı bir örnek için `GetColumnInfo` bkz. [tüketiciye döndürülen sütunları dinamik olarak belirleme](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonu mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
