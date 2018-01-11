---
title: "CL komut dosyaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: cl
dev_langs: C++
helpviewer_keywords:
- cl.exe compiler, command files
- command files
- command files, CL compiler
ms.assetid: ec3cea06-2af0-4fe9-a94c-119c9d31b3a9
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a711b2f4a484a6370af828c5d0aad522686ca3f1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cl-command-files"></a>CL Komut Dosyaları
Bir komut dosyası seçenekleri ve aksi durumda yazarsınız üzerinde dosya adlarını içeren bir metin dosyasıdır [komut satırı](../../build/reference/compiler-command-line-syntax.md) veya kullanarak belirtin [CL ortam değişkeni](../../build/reference/cl-environment-variables.md). CL derleyici komut dosyasını CL ortam değişkeni veya komut satırı bağımsız değişken olarak kabul eder. Komut satırında veya CL ortam değişkeninde olanın aksine, komut dosyası birden fazla satırı seçeneği ve dosya adı kullanmanıza izin verir.  
  
 Seçenekleri ve bir komut dosyası adlarında komutu filename CL ortam değişkeni içinde veya komut satırında konumuna göre işlenir. Bununla birlikte, / Link seçeneği komut dosyasında görünürse, satırın geri kalan tüm seçenekleri bağlayıcıya geçirilir. Komut dosyası izleyen satırlarında ve komut dosyası çağırma sonra komut satırında seçeneklerini hala derleyici seçeneği olarak kabul edilir. Seçenekleri sırası kendi yorumlama nasıl etkilediği hakkında daha fazla bilgi için bkz: [CL seçenekleri sırası](../../build/reference/order-of-cl-options.md).  
  
 Bir komut dosyası CL komut içermemesi gerekir. Her seçenek başlamalı ve aynı satırda son; ters eğik çizgi kullanamazsınız (\\) iki satır bir seçenek birleştirmek için.  
  
 Bir komut dosyası tarafından belirtilen bir at işareti (@) tarafından bir dosya adı; ardından Dosya adı, mutlak veya göreli bir yol belirtebilirsiniz.  
  
 Örneğin, aşağıdaki komutu yanıt adındaki bir dosyada ise:  
  
```  
/Og /link LIBC.LIB  
```  
  
 ve aşağıdaki CL komut belirtin:  
  
```  
CL /Ob2 @RESP MYAPP.C  
```  
  
 CL komutu aşağıdaki gibidir:  
  
```  
CL /Ob2 /Og MYAPP.C /link LIBC.LIB  
```  
  
 Komut satırı ve komut dosyası komutları etkili bir şekilde birleştirilir unutmayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)