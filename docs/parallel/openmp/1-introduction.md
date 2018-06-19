---
title: 1. Giriş | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c42e72bc-0e31-4b1c-b670-cd82673c0c5a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 883af9cb48a0fb13dbb9a758d6f8174096d4c0c3
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33685846"
---
# <a name="1-introduction"></a>1. Giriş
Bu belge derleyici yönergeleri, kitaplık işlevleri ve paylaşılan bellek paralellik C ve C++ programlarında belirtmek için kullanılan ortam değişkenlerinin koleksiyonunu belirtir. Bu belgede açıklanan işlevselliği topluca olarak bilinen *OpenMP C/C++ uygulama programı arabirimi (API)*. Bu belirtimi paralel, programlama modeli sağlamak için paylaşılan bellek mimarileri farklı satıcılardan arasında taşınabilmesini programın veren hedefidir. OpenMP C/C++ API çok sayıda satıcılardan derleyicileri tarafından desteklenmez. OpenMP hakkında daha fazla bilgi dahil olmak üzere *OpenMP Fortran uygulama programı arabirimi*, aşağıdaki web sitesinde bulunabilir:  
  
 [http://www.openmp.org](http://www.openmp.org)  
  
 Yönergeleri, kitaplık işlevleri ve bu belgede tanımlanan ortam değişkenleri oluşturmak ve taşınabilirlik izin veren paralel programları yönetmek kullanıcılara izin verir. Yönergeleri C genişletmek ve C++ sıralı programlama modeli ile tek bir program birden çok veri (SPMD) yapıları, iş paylaşım yapıları ve eşitleme yapıları ve Destek paylaşımı ve veri privatization sağlarlar. OpenMP C ve C++ API desteği derleyicileri etkinleştirir ve tüm OpenMP derleyici yönergeleri yorumu sağlayan derleyici komut satırı seçeneğini dahil edilir.