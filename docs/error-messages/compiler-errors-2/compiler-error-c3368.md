---
title: Derleyici Hatası C3368 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3368
dev_langs:
- C++
helpviewer_keywords:
- C3368
ms.assetid: 5bfd5be4-dfa9-4b33-9612-010561b40955
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 438f9a4f23dd7069457a635c0db02b66ff8de1e8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33251179"
---
# <a name="compiler-error-c3368"></a>Derleyici Hatası C3368
'işlevi bildiriminde': IDL için geçersiz çağırma kuralı  
  
 Yalnızca kullanabilirsiniz [__stdcall](../../cpp/stdcall.md) veya [__cdecl](../../cpp/cdecl.md) bir .idl dosyasında çağırma kuralları.  
  
 Aşağıdaki örnek C3368 oluşturur:  
  
```  
// C3368.cpp  
// processor: x86  
[idl_module(name="Name", dllname="Some.dll")];  
  
[idl_module(name="Name")]  
int __fastcall f1();   // C3368  
```