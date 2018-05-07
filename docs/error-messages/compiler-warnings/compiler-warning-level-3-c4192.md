---
title: Derleyici Uyarısı (Düzey 3) C4192 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4192
dev_langs:
- C++
helpviewer_keywords:
- C4192
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3bae9b7af95de94b8f667cb09710af21044f8b80
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4192"></a>Derleyici Uyarısı (Düzey 3) C4192
'name' 'Kitaplığı' tür kitaplığını içeri aktarma sırasında otomatik olarak hariç  
  
 A `#import` kitaplığını içeren bir öğeyi *adı*, diğer bir deyişle Win32 sistem üstbilgilerinde de tanımlanabilir. Tür kitaplıkları sınırlamaları nedeniyle, gibi adları **IUnknown** veya GUID genellikle tanımlanmış bir tür kitaplığı sistem üstbilgileri tanımından çoğaltma. `#import` Bu öğeler algılar ve .tlh ve .tli üstbilgi dosyalarında eklemenizi reddeder.  
  
 Bu davranışı geçersiz kılmak için kullanın `#import` öznitelikleri [no_auto_exclude](../../preprocessor/no-auto-exclude.md) ve [include()](../../preprocessor/include-parens.md).