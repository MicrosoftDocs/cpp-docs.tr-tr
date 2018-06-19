---
title: Derleyici Hatası C3370 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3370
dev_langs:
- C++
helpviewer_keywords:
- C3370
ms.assetid: ee6d4c85-78fc-42b2-836e-5cc491a3b2ba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 427a389de4d391cea059b5b7ef601016dea98d2f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33256453"
---
# <a name="compiler-error-c3370"></a>Derleyici Hatası C3370
'idl_module name': idl_module henüz tanımlanmadı.  
  
 Kullanmadan önce [idl_module](../../windows/idl-module.md) bir DLL'deki giriş noktası belirtmek için önce kullanmanız gerekir `idl_module` DLL adını belirtin.  
  
 Aşağıdaki örnek C3370 oluşturur:  
  
```  
// C3370.cpp  
[module(name=MyLibrary)];  
// uncomment the following line to resolve the error  
// [idl_module(name="name1", dllname=x.dll)];  
[idl_module(name="name1"), entry(100)] // C3370  
int f1();  
  
int main()  
{  
}  
```