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
ms.openlocfilehash: 6b53410c8116f88d51734bb302026a03994e520a
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338200"
---
# <a name="user-record"></a>Kullanıcı Kaydı
Kullanıcı kaydı, bir satır için sütun verileri temsil eden kod ve veri yapısı sağlar. Bir kullanıcı kaydı, derleme zamanında veya çalışma zamanında oluşturulabilir. ATL OLE DB sağlayıcısı Sihirbazı ile bir sağlayıcı oluşturduğunuzda, sihirbaz ("MyProvider" bir sağlayıcı adı [kısa adı] belirtilen varsayılarak) şuna benzer bir varsayılan kullanıcı kaydı oluşturur:  
  
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
  
 OLE DB sağlayıcı şablonları istemcisi ile ilgili tüm OLE DB özellikleri işler. Bir yanıt için gerekli olan sütun verileri almak için sağlayıcı çağırır `GetColumnInfo` işlevin kullanıcı kaydında yerleştirmeniz gerekir. Açıkça geçersiz kılabilirsiniz `GetColumnInfo` kullanıcı kaydında gibi bildirerek .h dosyasındaki burada gösterildiği gibi:  
  
```cpp  
template <class T>  
static ATLCOLUMNINFO* GetColumnInfo(T* pThis, ULONG* pcCols)   
```  
  
 Bu eşdeğerdir.  
  
```cpp  
static ATLCOLUMNINFO* GetColumnInfo(CommandClass* pThis, ULONG* pcCols)  
static ATLCOLUMNINFO* GetColumnInfo(RowsetClass* pThis, ULONG* pcCols)  
```  
  
 Ayrıca uygulamalıdır `GetColumnInfo` kullanıcı kaydının .cpp dosyası içinde.  
  
 PROVIDER_COLUMN_MAP makroları yardımcı oluştururken bir `GetColumnInfo` işlevi:  
  
-   BEGIN_PROVIDER_COLUMN_MAP işlev prototipi ve statik bir dizi tanımlar `ATLCOLUMNINFO` yapıları.  
  
-   PROVIDER_COLUMN_ENTRY tanımlar ve tek bir başlatır `ATLCOLUMNINFO`.  
  
-   END_PROVIDER_COLUMN_MAP dizi ve işlev kapatır. Ayrıca bir dizi öğe sayısını yerleştirir *pcCols* parametresi.  
  
 Çalışma zamanında, bir kullanıcı kaydı oluşturulduğunda `GetColumnInfo` kullanan *pThis* satır kümesi veya komut örneğine bir işaretçi almak için parametre. Komutlar ve satır kümeleri desteklemelidir `IColumnsInfo` sütun bilgileri bu işaretçiyle alınabilmesi için arabirim.  
  
 `CommandClass` ve `RowsetClass` komut ve kullanıcı kaydını kullanan satır kümesi.  
  
 Geçersiz kılmak daha ayrıntılı bir örnek `GetColumnInfo` bir kullanıcı kaydı görebilirsiniz [dinamik olarak belirleme sütunları döndürülen tüketici](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)