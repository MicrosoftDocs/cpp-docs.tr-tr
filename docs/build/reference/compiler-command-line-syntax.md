---
title: Derleyici komut satırı sözdizimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- syntax, CL compiler command line
- cl.exe compiler, command-line syntax
ms.assetid: acba2c1c-0803-4a3a-af25-63e849b930a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 825121a111d47de6b012aad444907363ad8c2a36
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32370127"
---
# <a name="compiler-command-line-syntax"></a>Derleyici Komut Satırı Sözdizimi
CL komut satırı aşağıdaki söz dizimini kullanır:  
  
```  
CL [option...] file... [option | file]... [lib...] [@command-file] [/link link-opt...]  
```  
  
 Aşağıdaki tabloda CL komut için giriş açıklanmaktadır.  
  
|Giriş|Açıklama|  
|-----------|-------------|  
|*Seçeneği*|Bir veya daha fazla [CL seçenekleri](../../build/reference/compiler-options.md). Tüm seçenekleri tüm belirtilen kaynak dosyaları için geçerli olduğunu unutmayın. Seçenekler, eğik çizgi (/) veya tire (-) tarafından belirtilir. Bir boşluk seçenek ve bağımsız değişkenleri arasında izin verilip verilmeyeceğini bir seçenek bağımsız değişken, seçeneğin açıklama belgeleri sürerse. (Dışında/Help seçeneği) seçeneği adları büyük/küçük harfe duyarlıdır. Bkz: [CL seçenekleri sırası](../../build/reference/order-of-cl-options.md) daha fazla bilgi için.|  
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