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
ms.workload: cplusplus
ms.openlocfilehash: 022c0e0aac8d231963ddf6d5d3715d55f726a8b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4192"></a>Derleyici Uyarısı (Düzey 3) C4192
'name' 'Kitaplığı' tür kitaplığını içeri aktarma sırasında otomatik olarak hariç  
  
 A `#import` kitaplığını içeren bir öğeyi *adı*, diğer bir deyişle Win32 sistem üstbilgilerinde de tanımlanabilir. Tür kitaplıkları sınırlamaları nedeniyle, gibi adları **IUnknown** veya GUID genellikle tanımlanmış bir tür kitaplığı sistem üstbilgileri tanımından çoğaltma. `#import`Bu öğeler algılar ve .tlh ve .tli üstbilgi dosyalarında eklemenizi reddeder.  
  
 Bu davranışı geçersiz kılmak için kullanın `#import` öznitelikleri [no_auto_exclude](../../preprocessor/no-auto-exclude.md) ve [include()](../../preprocessor/include-parens.md).