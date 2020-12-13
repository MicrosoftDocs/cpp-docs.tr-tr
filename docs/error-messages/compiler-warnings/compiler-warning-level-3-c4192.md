---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 3) C4192'
title: Derleyici Uyarısı (düzey 3) C4192
ms.date: 11/04/2016
f1_keywords:
- C4192
helpviewer_keywords:
- C4192
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
ms.openlocfilehash: 8cfebf1845c578723bab5622e18699c0282d4c4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344230"
---
# <a name="compiler-warning-level-3-c4192"></a>Derleyici Uyarısı (düzey 3) C4192

' Library ' tür kitaplığı içeri aktarılırken ' name ' otomatik olarak hariç tutulanıyor

Bir `#import` kitaplık, Win32 sistem üst bilgilerinde de tanımlanan bir öğe *adı* içerir. Tür kitaplıklarının sınırlamaları nedeniyle, **IUnknown** veya GUID gibi adlar genellikle bir tür kitaplığında tanımlanmıştır ve bu da tanımı sistem başlıklarından çoğaltma. `#import` , bu öğeleri algılar ve. tlh ve. TLI üst bilgi dosyalarında dahil etmek için reddeder.

Bu davranışı geçersiz kılmak için `#import` [no_auto_exclude](../../preprocessor/no-auto-exclude.md) öznitelikleri kullanın ve [() ekleyin](../../preprocessor/include-parens.md).
