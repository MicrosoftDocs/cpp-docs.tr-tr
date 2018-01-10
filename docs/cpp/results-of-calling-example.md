---
title: "Çağırma örneği sonuçları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- examples [C++], results of calling
- results, thiscall call
- results, __fastcall keyword call
- results, __cdecl call
- results, __stdcall call
ms.assetid: aa70a7cb-ba1d-4aa6-bd0a-ba783da2e642
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: eaa47af17e46f51ef92cc15b8d2275b2ed8e05f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="results-of-calling-example"></a>Çağırma Örneği Sonuçları
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
  
## <a name="cdecl"></a>__cdecl  
 C düzenlenmiş işlevi adıdır "_MyFunc."  
  
 ![Cdecl arama kuralı](../cpp/media/vc37i01.gif "vc37I01")  
__Cdecl çağırma  
  
## <a name="stdcall-and-thiscall"></a>__stdcall ve thiscall  
 C donatılmış adı (`__stdcall`) olan "_MyFunc@20." Özel donatılmış C++ adıdır.  
  
 ![&#95; &#95; stdcall ve thiscall çağırma kuralları](../cpp/media/vc37i02.gif "vc37I02")  
__Stdcall ve thiscall çağırma kuralları  
  
## <a name="fastcall"></a>__fastcall  
 C donatılmış adı (`__fastcall`) olan "@MyFunc@20." Özel donatılmış C++ adıdır.  
  
 ![Çağırma kuralı için &#95; &#95; fastcall](../cpp/media/vc37i03.gif "vc37I03")  
__Fastcall çağırma  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çağırma Örneği: İşlev Prototipi ve Çağrı](../cpp/calling-example-function-prototype-and-call.md)