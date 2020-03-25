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
ms.openlocfilehash: edbeb187e568b833673d91ef70ff57fbd460659c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179061"
---
# <a name="results-of-calling-example"></a>Çağırma Örneği Sonuçları

**Microsoft 'a özgü**

## <a name="__cdecl"></a>__cdecl

C ile donatılmış işlev adı `_MyFunc`.

![CDECL çağırma kuralı](../cpp/media/vc37i01.gif "CDECL çağırma kuralı") <br/>
**__Cdecl** çağırma kuralı

## <a name="__stdcall-and-thiscall"></a>__stdcall ve thiscall

C düzenlenmiş adı ( **__stdcall**) `_MyFunc@20`. C++ Düzenlenmiş ad uygulamaya özgüdür.

![&#95;&#95;stdcall ve thiscall çağırma kuralları](../cpp/media/vc37i02.gif "&#95;&#95;stdcall ve thiscall çağırma kuralları") <br/>
__Stdcall ve thiscall çağırma kuralları

## <a name="__fastcall"></a>__fastcall

C düzenlenmiş adı ( **__fastcall**) `@MyFunc@20`. C++ Düzenlenmiş ad uygulamaya özgüdür.

![Fastcall için &#95; &#95;çağrı kuralı](../cpp/media/vc37i03.gif "Fastcall için &#95; &#95;çağrı kuralı") <br/>
__Fastcall çağırma kuralı

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Çağırma Örneği: İşlev Prototipi ve Çağrı](../cpp/calling-example-function-prototype-and-call.md)
