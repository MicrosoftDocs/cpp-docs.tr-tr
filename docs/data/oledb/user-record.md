---
title: Kullanıcı kaydı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- records, user
- OLE DB providers, user record
- user records
- user records, described
- rowsets, user record
ms.assetid: 9c0d2864-2738-4f62-a750-1016d9c3523f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e37ed0ac918b004513aa64308870a534a7b2af40
ms.sourcegitcommit: 840033ddcfab51543072604ccd5656fc6d4a5d3a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2018
ms.locfileid: "50216298"
---
# <a name="user-record"></a>Kullanıcı Kaydı

Kullanıcı kaydı, bir satır için sütun verileri temsil eden kod ve veri yapısı sağlar. Bir kullanıcı kaydı, derleme zamanında veya çalışma zamanında oluşturulabilir. İle bir sağlayıcı oluşturduğunuzda **ATL OLE DB sağlayıcısı Sihirbazı**, şuna benzer bir varsayılan kullanıcı kaydı sihirbaz oluşturur (bir sağlayıcı adı [kısa adı] belirtilen varsayılarak *MyProvider*):

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

OLE DB sağlayıcı şablonları tüm OLE DB ayrıntılarına istemci etkileşim bağlı işleyin. Bir yanıt için gerekli olan sütun verileri almak için sağlayıcı çağırır `GetColumnInfo` işlevin kullanıcı kaydında yerleştirmeniz gerekir. Açıkça geçersiz kılabilirsiniz `GetColumnInfo` kullanıcı kaydında gibi bildirerek .h dosyasındaki burada gösterildiği gibi:

```cpp
template <class T>
static ATLCOLUMNINFO* GetColumnInfo(T* pThis, ULONG* pcCols) 
```

Bu karşılık gelir:

```cpp
static ATLCOLUMNINFO* GetColumnInfo(CommandClass* pThis, ULONG* pcCols)
static ATLCOLUMNINFO* GetColumnInfo(RowsetClass* pThis, ULONG* pcCols)
```

Ardından, uygulama `GetColumnInfo` kullanıcı kaydının .cpp dosyası içinde.

PROVIDER_COLUMN_MAP makroları yardımcı oluştururken bir `GetColumnInfo` işlevi:

- BEGIN_PROVIDER_COLUMN_MAP işlev prototipi ve statik bir dizi tanımlar `ATLCOLUMNINFO` yapıları.

- PROVIDER_COLUMN_ENTRY tanımlar ve tek bir başlatır `ATLCOLUMNINFO`.

- END_PROVIDER_COLUMN_MAP dizi ve işlev kapatır. Ayrıca bir dizi öğe sayısını yerleştirir *pcCols* parametresi.

Çalışma zamanında, bir kullanıcı kaydı oluşturulduğunda `GetColumnInfo` kullanan *pThis* satır kümesi veya komut örneğine bir işaretçi almak için parametre. Komutlar ve satır kümeleri desteklemelidir `IColumnsInfo` sütun bilgileri bu işaretçiyle alınması için arabirim.

`CommandClass` ve `RowsetClass` komut ve kullanıcı kaydını kullanan satır kümesi.

Geçersiz kılmak daha ayrıntılı bir örnek `GetColumnInfo` bir kullanıcı kaydı görebilirsiniz [dinamik olarak belirleme sütunları döndürülen tüketici](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
