---
title: "space_info yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: filesystem/std::tr2::sys::space_info
dev_langs: C++
ms.assetid: f2b35b42-06ff-45bd-8617-39a0f5358a54
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b59a50a4040756ffb32cda12c6abb08ba0cfbe1d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="spaceinfo-structure"></a>space_info Yapısı
Bir birim ilgili bilgileri tutar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct space_info   {
    uintmax_t capacity;
    uintmax_t free;
    uintmax_t available;
    };  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`unsigned long long available`|Birimdeki veriler temsil etmek kullanılabilir bayt sayısını temsil eder.|  
|`unsigned long long capacity`|Birim sunan bayt toplam sayısını temsil eder.|  
|`unsigned long long free`|Birimdeki veriler temsil etmek için kullanılan değil bayt sayısını temsil eder.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<filesystem >  
  
 **Namespace:** std::experimental::filesystem  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [\<FileSystem >](../standard-library/filesystem.md)   
 [alanı](http://msdn.microsoft.com/en-us/7fce0b0e-523b-4598-b218-47245d0204ca)   
 [Dosya sistemi gezintisi (C++)](../standard-library/file-system-navigation.md)

