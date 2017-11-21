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
ms.openlocfilehash: b1a6a450c0c3faca9088b01e1016df5f4e5a4045
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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