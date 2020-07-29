---
title: Çağırma Örneği Sonuçları
ms.date: 11/19/2018
helpviewer_keywords:
- examples [C++], results of calling
- results, thiscall call
- results, __fastcall keyword call
- results, __cdecl call
- results, __stdcall call
ms.assetid: aa70a7cb-ba1d-4aa6-bd0a-ba783da2e642
ms.openlocfilehash: 1bf5fe62b8ef2b7a37bf72b7a40e5d47af3f3961
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225884"
---
# <a name="results-of-calling-example"></a>Çağırma Örneği Sonuçları

**Microsoft'a Özgü**

## <a name="__cdecl"></a>__cdecl

C ile donatılmış işlev adı `_MyFunc` .

![CDECL çağırma kuralı](../cpp/media/vc37i01.gif "CDECL çağırma kuralı") <br/>
**`__cdecl`** Çağırma kuralı

## <a name="__stdcall-and-thiscall"></a>__stdcall ve thiscall

C düzenlenmiş adı ( **`__stdcall`** ), `_MyFunc@20` . C++ düzenlenmiş adı uygulamaya özgüdür.

![&#95;&#95;stdcall ve thiscall çağırma kuralları](../cpp/media/vc37i02.gif "&#95;&#95;stdcall ve thiscall çağırma kuralları") <br/>
__Stdcall ve thiscall çağırma kuralları

## <a name="__fastcall"></a>__fastcall

C düzenlenmiş adı ( **`__fastcall`** ), `@MyFunc@20` . C++ düzenlenmiş adı uygulamaya özgüdür.

![ &#95;&#95;fastcall için çağrı kuralı](../cpp/media/vc37i03.gif " &#95;&#95;fastcall için çağrı kuralı") <br/>
__Fastcall çağırma kuralı

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Çağırma örneği: Işlev prototipi ve çağrı](../cpp/calling-example-function-prototype-and-call.md)
