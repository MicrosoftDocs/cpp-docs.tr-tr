---
title: Çağırma örneği sonuçları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 9c49457aecb93b16ffb294f88e4f6643826492e2
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39465704"
---
# <a name="results-of-calling-example"></a>Çağırma Örneği Sonuçları
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
  
## <a name="cdecl"></a>__cdecl  
 "_MyFunc." C düzenlenmiş işlev adıdır  
  
 ![Çağırma kuralı CDECL](../cpp/media/vc37i01.gif "vc37I01")  
**__Cdecl** çağırma kuralı  
  
## <a name="stdcall-and-thiscall"></a>__stdcall ve thiscall  
 C ile düzenlenmiş adı (**__stdcall**) olan "_MyFunc@20." C++ ile düzenlenmiş adın özel.  
  
 ![&#95;&#95;stdcall ve thiscall çağırma kuralları](../cpp/media/vc37i02.gif "vc37I02")  
__Stdcall ve thiscall çağırma kuralları  
  
## <a name="fastcall"></a>__fastcall  
 C ile düzenlenmiş adı (**__fastcall**) olan "@MyFunc@20." C++ ile düzenlenmiş adın özel.  
  
 ![Çağırma kuralı için &#95; &#95;fastcall](../cpp/media/vc37i03.gif "vc37I03")  
__Fastcall çağırma kuralı  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Çağırma Örneği: İşlev Prototipi ve Çağrı](../cpp/calling-example-function-prototype-and-call.md)