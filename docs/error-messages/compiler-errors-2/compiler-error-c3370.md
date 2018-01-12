---
title: "Derleyici Hatası C3370 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3370
dev_langs: C++
helpviewer_keywords: C3370
ms.assetid: ee6d4c85-78fc-42b2-836e-5cc491a3b2ba
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 01ca951f6acd8af2fbbdba3d84b82a441cd7e92b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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