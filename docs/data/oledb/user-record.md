---
title: "Kullanıcı kaydı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- records, user
- OLE DB providers, user record
- user records
- user records, described
- rowsets, user record
ms.assetid: 9c0d2864-2738-4f62-a750-1016d9c3523f
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 08b0e369629bc93002ee73a31978ef8d00493f6d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="user-record"></a>Kullanıcı Kaydı
Kullanıcı kaydı satır için sütun verisini temsil eden kod ve veri yapısı sağlar. Bir kullanıcı kaydı derleme zamanında veya çalışma zamanında oluşturulabilir. ATL OLE DB Sağlayıcı Sihirbazı'nı kullanarak bir sağlayıcı oluşturduğunuzda, Sihirbazı'nı ("MyProvider" sağlayıcı adını [kısa ad] belirttiğiniz varsayılarak) şöyle bir varsayılan kullanıcı kaydı oluşturur:  
  
```  
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
  
 OLE DB sağlayıcı şablonları etkileşimleri istemcisi ile ilgili tüm OLE DB özellikleri işler. Yanıt için gereken sütun veri almaya sağlayıcısı çağıran `GetColumnInfo` kullanıcı kaydına yerleştirmeniz gereken işlev. Açıkça geçersiz kılabilirsiniz `GetColumnInfo` kullanıcı kaydı, örneğin, bildirerek .h dosyasında aşağıda gösterildiği gibi:  
  
```  
template <class T>  
static ATLCOLUMNINFO* GetColumnInfo(T* pThis, ULONG* pcCols)   
```  
  
 Bu eşdeğerdir:  
  
```  
static ATLCOLUMNINFO* GetColumnInfo(CommandClass* pThis, ULONG* pcCols)  
static ATLCOLUMNINFO* GetColumnInfo(RowsetClass* pThis, ULONG* pcCols)  
```  
  
 Ayrıca uygulamalıdır `GetColumnInfo` kullanıcı kaydının .cpp dosyasında.  
  
 PROVIDER_COLUMN_MAP makroları yardımcı oluşturmada bir `GetColumnInfo` işlevi:  
  
-   BEGIN_PROVIDER_COLUMN_MAP tanımlar işlev prototipi ve statik bir dizi **ATLCOLUMNINFO** yapıları.  
  
-   PROVIDER_COLUMN_ENTRY tanımlar ve tek bir başlatır **ATLCOLUMNINFO**.  
  
-   END_PROVIDER_COLUMN_MAP diziyi ve işlevi kapatır. Ayrıca bir dizi öğe sayısını yerleştirir `pcCols` parametresi.  
  
 Çalışma zamanında, bir kullanıcı kaydı oluşturulduğunda **GetColumnInfo** kullanan `pThis` satır kümesi veya komut örneğine bir işaretçi almak için parametre. Komutlar ve satır kümeleri desteklemelidir `IColumnsInfo` sütun bilgileri bu işaretçiyle alınabilmesi için arabirim.  
  
 **CommandClass** ve **RowsetClass** komut ve kullanıcı kaydını kullanan satır kümesidir.  
  
 Geçersiz kılmak nasıl daha ayrıntılı bir örnek için `GetColumnInfo` bir kullanıcı kaydındaki bkz [dinamik olarak belirleme sütunları döndürülen tüketici](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)