---
title: Çağırma örneği sonuçları | Microsoft Docs
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- examples [C++], results of calling
- results, thiscall call
- results, __fastcall keyword call
- results, __cdecl call
- results, __stdcall call
ms.assetid: aa70a7cb-ba1d-4aa6-bd0a-ba783da2e642
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5687adfada8657ae26edd9001db8990ff08864e9
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894704"
---
# <a name="results-of-calling-example"></a>Çağırma Örneği Sonuçları

**Microsoft'a özgü**

## <a name="cdecl"></a>__cdecl
C işlev düzenlenmiş adı `_MyFunc`.

![Çağırma kuralı CDECL](../cpp/media/vc37i01.gif "vc37I01")  
**__Cdecl** çağırma kuralı

## <a name="stdcall-and-thiscall"></a>__stdcall ve thiscall

C ile düzenlenmiş adı (**__stdcall**) olan `_MyFunc@20`. C++ ile düzenlenmiş adın uygulamasına özgüdür.

![&#95;&#95;stdcall ve thiscall çağırma kuralları](../cpp/media/vc37i02.gif "vc37I02")  
__Stdcall ve thiscall çağırma kuralları

## <a name="fastcall"></a>__fastcall

C ile düzenlenmiş adı (**__fastcall**) olan `@MyFunc@20`. C++ ile düzenlenmiş adın uygulamasına özgüdür.

![Çağırma kuralı için &#95; &#95;fastcall](../cpp/media/vc37i03.gif "vc37I03")  
__Fastcall çağırma kuralı

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Çağırma Örneği: İşlev Prototipi ve Çağrı](../cpp/calling-example-function-prototype-and-call.md)