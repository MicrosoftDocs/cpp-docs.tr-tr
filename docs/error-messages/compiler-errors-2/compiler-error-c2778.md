---
title: Derleyici Hatası C2778 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2778
dev_langs:
- C++
helpviewer_keywords:
- C2778
ms.assetid: b24cb732-2914-42cc-8928-e2d87b393428
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5f8747c0f2d0434f034ac0a0b84dcce510de0e96
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33235097"
---
# <a name="compiler-error-c2778"></a>Derleyici Hatası C2778
__declspec(uuid()) Düzensiz biçimlendirilmiş GUID  
  
 Yanlış bir GUID için sağlanan [UUID](../../cpp/uuid-cpp.md) genişletilmiş öznitelik.  
  
 GUID, onaltılık sayı aşağıdaki biçimde bir dize olması gerekir:  
  
```  
// C2778a.cpp  
// compile with: /c  
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};  
struct __declspec(uuid("{00000000-0000-0000-0000-000000000000}")) B{};  
```  
  
 `uuid` Genişletilmiş öznitelik kabul tarafından tanınan dizeleri [CLSIDFromString](http://msdn.microsoft.com/library/windows/desktop/ms680589), ile veya parantezi sınırlayıcıları olmadan.  
  
 Aşağıdaki örnek C2778 oluşturur:  
  
```  
// C2778b.cpp  
struct __declspec(uuid(" 00000000-0000-0000-0000-000000000000 ")) C { };   // C2778  
struct __declspec(uuid("00000000000000000000000000000000")) D { };   // C2778  
```