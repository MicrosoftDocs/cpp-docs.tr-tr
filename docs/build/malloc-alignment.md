---
title: malloc hizalaması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a8d1d1b4-5122-456f-9a64-a50e105e55a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d503d0dd891c651a405cb79bb5ce50996f46cff6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="malloc-alignment"></a>malloc Hizalaması
[malloc](../c-runtime-library/reference/malloc.md) temel hizalama ve, herhangi bir nesne depolama tahsis edilen bellek miktarında sığacak için uygun hizalanır bellek döndürmek için sağlanır. A *temel hizalama* bir hizalama belirtimi olmadan uygulaması tarafından desteklenen en büyük hizalama küçük veya ona eşit bir hizalama. (Visual C++'da, bu için gerekli hizalama olan bir `double`, veya 8 bayt. 64 bit platformları hedefler kodda, 16 bayt'tır.) Örneğin, dört bayt ayırma dört bayt veya daha küçük nesne destekleyen bir sınır hizalı.  
  
 Visual C++ türlerine izin verir *hizalama Genişletilmiş*, olarak da bilinen olduğu *aşırı hizalı* türleri. Örneğin, SSE türleri [__m128](../cpp/m128.md) ve `__m256`ve kullanarak belirtilen türlerine `__declspec(align( n ))` burada `n` 8'den büyükse, hizalama uzattınız. Bellek hizalama genişletilmiş hizalama gerektiren bir nesne için uygun bir sınırında tarafından garanti edilmez `malloc`. Aşırı hizalanmış türleri için bellek ayırmak için kullanır [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) ve ilgili işlevleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yığın kullanımı](../build/stack-usage.md)   
 [Hizalama](../cpp/align-cpp.md)   
 [__declspec](../cpp/declspec.md)