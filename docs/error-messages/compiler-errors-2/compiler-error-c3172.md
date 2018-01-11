---
title: "Derleyici Hatası C3172 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3172
dev_langs: C++
helpviewer_keywords: C3172
ms.assetid: 1834e2fd-6036-4c33-aff2-b51bc7c99441
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3390c0f1f566e28bc6a000b2ff570c781c93bc98
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3172"></a>Derleyici Hatası C3172
'module_name': bir projede farklı idl_module öznitelikleri belirtilemez  
  
 [idl_module](../../windows/idl-module.md) aynı özniteliklerle ancak farklı ad `dllname` veya `version` parametreleri iki bir derleme dosyalarında bulundu. Yalnızca bir benzersiz `idl_module` derlemesi başına özniteliği belirtilebilir.  
  
 Aynı `idl_module` öznitelikleri birden fazla kaynak kodu dosyasına belirtilebilir.  
  
 Örneğin, aşağıdaki `idl_module` öznitelikleri bulundu:  
  
```  
// C3172.cpp  
[module(name="MyMod")];  
[ idl_module(name="x", dllname="file.dll", version="1.1") ];  
int main() {}  
```  
  
 Ardından,  
  
```  
// C3172b.cpp  
// compile with: C3172.cpp  
// C3172 expected  
[ idl_module(name="x", dllname="file.dll", version="1.0") ];  
```  
  
 Derleyici C3172 oluşturur (farklı sürüm değerleri unutmayın).