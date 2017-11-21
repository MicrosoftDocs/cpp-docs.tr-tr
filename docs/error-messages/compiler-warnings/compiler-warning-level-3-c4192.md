---
title: "Derleyici Uyarısı (Düzey 3) C4192 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4192
dev_langs: C++
helpviewer_keywords: C4192
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ff07a7fd5af7c9e4d73d9a4ce679edc7ab5e6b43
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4192"></a>Derleyici Uyarısı (Düzey 3) C4192
'name' 'Kitaplığı' tür kitaplığını içeri aktarma sırasında otomatik olarak hariç  
  
 A `#import` kitaplığını içeren bir öğeyi *adı*, diğer bir deyişle Win32 sistem üstbilgilerinde de tanımlanabilir. Tür kitaplıkları sınırlamaları nedeniyle, gibi adları **IUnknown** veya GUID genellikle tanımlanmış bir tür kitaplığı sistem üstbilgileri tanımından çoğaltma. `#import`Bu öğeler algılar ve .tlh ve .tli üstbilgi dosyalarında eklemenizi reddeder.  
  
 Bu davranışı geçersiz kılmak için kullanın `#import` öznitelikleri [no_auto_exclude](../../preprocessor/no-auto-exclude.md) ve [include()](../../preprocessor/include-parens.md).