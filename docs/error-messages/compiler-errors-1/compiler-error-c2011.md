---
title: "Derleyici Hatası C2011 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2011
dev_langs:
- C++
helpviewer_keywords:
- C2011
ms.assetid: 992c9d51-e850-4d53-b86b-02e73b38249c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c599d6add1fa51c6aae7f04019eacdc94f11bb15
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2011"></a>Derleyici Hatası C2011
'tanımlayıcısı': 'type' yazın yeniden tanımlama  
  
 Tanımlayıcı olarak zaten tanımlandı `type`. Tanımlayıcının yeniden denetleyin.  
  
 Üstbilgi dosyası içe aktarırsanız veya birden çok kez aynı dosyaya tür kitaplığına C2011 elde edebilirsiniz. Kullanımını üstbilgi dosyasında tanımlanmış türlerinin birden çok içermeler önlemek için koruyucuları içerir veya `#pragma` [sonra](../../preprocessor/once.md) üstbilgi dosyasında yönergesi.  
  
 Yeniden tanımlanan türün ilk bildirimi bulmanız gerekiyorsa, kullanabileceğiniz [/P](../../build/reference/p-preprocess-to-a-file.md) önceden işlenmiş çıktı üretmek için derleyici bayrağı derleyiciye geçirildi. Metin arama araçları çıktı dosyasına yeniden tanımlanan tanımlayıcı örneklerini bulmak için kullanabilirsiniz.  
  
 Aşağıdaki örnek C2011 oluşturur ve bu düzeltmenin bir yolu gösterir:  
  
```  
// C2011.cpp  
// compile with: /c  
struct S;  
union S;   // C2011  
union S2;   // OK  
```