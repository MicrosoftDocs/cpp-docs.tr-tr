---
title: "Derleyici komut satırı sözdizimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- syntax, CL compiler command line
- cl.exe compiler, command-line syntax
ms.assetid: acba2c1c-0803-4a3a-af25-63e849b930a2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7fb89aca1990d44d7ef62ea76788b38e8ffa1d6d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-command-line-syntax"></a>Derleyici Komut Satırı Sözdizimi
CL komut satırı aşağıdaki söz dizimini kullanır:  
  
```  
CL [option...] file... [option | file]... [lib...] [@command-file] [/link link-opt...]  
```  
  
 Aşağıdaki tabloda CL komut için giriş açıklanmaktadır.  
  
|Giriş|Açıklama|  
|-----------|-------------|  
|*seçeneği*|Bir veya daha fazla [CL seçenekleri](../../build/reference/compiler-options.md). Tüm seçenekleri tüm belirtilen kaynak dosyaları için geçerli olduğunu unutmayın. Seçenekler, eğik çizgi (/) veya tire (-) tarafından belirtilir. Bir boşluk seçenek ve bağımsız değişkenleri arasında izin verilip verilmeyeceğini bir seçenek bağımsız değişken, seçeneğin açıklama belgeleri sürerse. (Dışında/Help seçeneği) seçeneği adları büyük/küçük harfe duyarlıdır. Bkz: [CL seçenekleri sırası](../../build/reference/order-of-cl-options.md) daha fazla bilgi için.|  
|`file`|Bir veya daha fazla kaynak dosyaları, .obj dosyaları ve kitaplıkları adı. CL kaynak dosyalarını derler ve .obj dosyaları ve kitaplıkları adları bağlayıcıya geçirir. Bkz: [CL dosya adı sözdizimi](../../build/reference/cl-filename-syntax.md) daha fazla bilgi için.|  
|*LIB*|Bir veya daha fazla kitaplık adları. CL bağlayıcı için bu adları geçirir.|  
|*komut dosyası*|Birden çok seçenekleri ve dosya adlarını içeren bir dosya. Bkz: [CL komut dosyaları](../../build/reference/cl-command-files.md) daha fazla bilgi için.|  
|*bağlantı iptal et*|Bir veya daha fazla [bağlayıcı seçenekleri](../../build/reference/linker-options.md). CL bu seçenekleri bağlayıcıya geçirir.|  
  
 Komut satırında karakter sayısını 1024, işletim sistemi tarafından dikte sınırı aşmadığından sürece seçenekleri, dosya adları ve kitaplık adları, herhangi bir sayıda belirtebilirsiniz.  
  
 Cl.exe dönüş değeri hakkında daha fazla bilgi için bkz: [cl.exe dönüş değerini](../../build/reference/return-value-of-cl-exe.md) .  
  
> [!NOTE]
>  Komut satırı giriş sınırı 1024 karakterle gelecekteki Windows sürümlerinde aynı kalacaksa garanti edilmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)