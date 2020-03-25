---
title: Derleyici Uyarısı (düzey 3) C4192
ms.date: 11/04/2016
f1_keywords:
- C4192
helpviewer_keywords:
- C4192
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
ms.openlocfilehash: 38b346e0a90729bda431b9cb578a03806be1ea4c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198984"
---
# <a name="compiler-warning-level-3-c4192"></a>Derleyici Uyarısı (düzey 3) C4192

' Library ' tür kitaplığı içeri aktarılırken ' name ' otomatik olarak hariç tutulanıyor

`#import` kitaplığı, Win32 sistem üst bilgilerinde de tanımlanan bir öğe *adı*içerir. Tür kitaplıklarının sınırlamaları nedeniyle, **IUnknown** veya GUID gibi adlar genellikle bir tür kitaplığında tanımlanmıştır ve bu da tanımı sistem başlıklarından çoğaltma. `#import`, bu öğeleri algılayacak ve. tlh ve. TLI üst bilgi dosyalarında dahil etmek için reddedecek.

Bu davranışı geçersiz kılmak için, `#import` öznitelikleri [no_auto_exclude](../../preprocessor/no-auto-exclude.md) ve [dahil et ()](../../preprocessor/include-parens.md)kullanın.
