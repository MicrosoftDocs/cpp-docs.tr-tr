---
title: Derleyici Hatası C2011 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2011
dev_langs:
- C++
helpviewer_keywords:
- C2011
ms.assetid: 992c9d51-e850-4d53-b86b-02e73b38249c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 898a724f022a81f590ec1f8165de9752de6c1d0b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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