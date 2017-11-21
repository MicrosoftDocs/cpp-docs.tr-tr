---
title: "(#import) yeniden adlandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Rename
dev_langs: C++
helpviewer_keywords: rename attribute
ms.assetid: 5c5c6153-1087-4b7b-87fb-fc59b90b9975
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6394d3b7aa53810d6dc57520401731f6d4603f51
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="rename-import"></a>rename (#import)
**C++ özel**  
  
 Ad çakışma sorunlarını çözmek çalışır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
rename("OldName","NewName")  
```  
  
#### <a name="parameters"></a>Parametreler  
 `OldName`  
 Tür kitaplığı eski adı.  
  
 `NewName`  
 Eski adı yerine kullanılacak adı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu öznitelik belirtilirse, derleyicinin tüm oluşumlarını değiştirir *EskiAd* kullanıcı tarafından sağlanan ile bir tür kitaplığı'nda *NewName* elde edilen üstbilgi dosyalarında.  
  
 Bu öznitelik, bir tür kitaplığı adı Sistem üstbilgi dosyaları makrosu tanımında ile örtüşür olduğunda kullanılabilir. Bu durum güvenilmedi sonra çeşitli sözdizimi hataları, gibi oluşturulmayacak [derleyici hatası C2059](../error-messages/compiler-errors-1/compiler-error-c2059.md) ve [derleyici hatası C2061](../error-messages/compiler-errors-1/compiler-error-c2061.md).  
  
> [!NOTE]
>  Tür Kitaplığı'nda, sonuçta elde edilen üstbilgi dosyasında kullanılan bir ad değil için adı için kullanılan bir yerini alır.  
  
 Örneğin, adında bir özellik varsayalım `MyParent` bir tür kitaplığı ve makro bulunmaktadır `GetMyParent` üstbilgi dosyasında tanımlanan ve önce kullanılan `#import`. Bu yana `GetMyParent` sarmalayıcı işlevi hata işleme için varsayılan ad olan **almak** özelliği, bir ad çakışması gerçekleşir. Sorunu çözmek için şu özniteliği kullanın `#import` deyimi:  
  
```  
rename("MyParent","MyParentX")  
```  
  
 ad yeniden adlandırır `MyParent` Tür Kitaplığı'nda. Yeniden adlandırma girişimi `GetMyParent` sarmalayıcı adı başarısız olur:  
  
```  
rename("GetMyParent","GetMyParentX")  
```  
  
 Bunun nedeni, ad `GetMyParent` elde edilen tür kitaplığı üstbilgi dosyası, yalnızca oluşur.  
  
 **Son C++ özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)   
 [#import yönergesi](../preprocessor/hash-import-directive-cpp.md)