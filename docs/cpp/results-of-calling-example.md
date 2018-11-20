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
ms.openlocfilehash: dcd1f9002362b7726883c6ce4f74fda9ab593544
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52175424"
---
# <a name="results-of-calling-example"></a>Çağırma Örneği Sonuçları

**Microsoft'a özgü**

## <a name="cdecl"></a>__cdecl

C işlev düzenlenmiş adı `_MyFunc`.

![Çağırma kuralı CDECL](../cpp/media/vc37i01.gif "CDECL çağırma kuralı") <br/>
**__Cdecl** çağırma kuralı

## <a name="stdcall-and-thiscall"></a>__stdcall ve thiscall

C ile düzenlenmiş adı (**__stdcall**) olan `_MyFunc@20`. C++ ile düzenlenmiş adın uygulamasına özgüdür.

![&#95;&#95;stdcall ve thiscall çağırma kuralları](../cpp/media/vc37i02.gif "&#95;&#95;stdcall ve thiscall çağırma kuralları") <br/>
__Stdcall ve thiscall çağırma kuralları

## <a name="fastcall"></a>__fastcall

C ile düzenlenmiş adı (**__fastcall**) olan `@MyFunc@20`. C++ ile düzenlenmiş adın uygulamasına özgüdür.

![Çağırma kuralı için &#95; &#95;fastcall](../cpp/media/vc37i03.gif "çağırma kuralı için &#95; &#95;fastcall") <br/>
__Fastcall çağırma kuralı

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Çağırma Örneği: İşlev Prototipi ve Çağrı](../cpp/calling-example-function-prototype-and-call.md)