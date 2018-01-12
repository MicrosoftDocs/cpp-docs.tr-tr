---
title: "1. Giriş | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c42e72bc-0e31-4b1c-b670-cd82673c0c5a
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f850e236ebfd056da93700df06ec830e5a573284
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="1-introduction"></a>1. Giriş
Bu belge derleyici yönergeleri, kitaplık işlevleri ve paylaşılan bellek paralellik C ve C++ programlarında belirtmek için kullanılan ortam değişkenlerinin koleksiyonunu belirtir. Bu belgede açıklanan işlevselliği topluca olarak bilinen *OpenMP C/C++ uygulama programı arabirimi (API)*. Bu belirtimi paralel, programlama modeli sağlamak için paylaşılan bellek mimarileri farklı satıcılardan arasında taşınabilmesini programın veren hedefidir. OpenMP C/C++ API çok sayıda satıcılardan derleyicileri tarafından desteklenmez. OpenMP hakkında daha fazla bilgi dahil olmak üzere *OpenMP Fortran uygulama programı arabirimi*, aşağıdaki web sitesinde bulunabilir:  
  
 [http://www.OpenMP.org](http://www.openmp.org)  
  
 Yönergeleri, kitaplık işlevleri ve bu belgede tanımlanan ortam değişkenleri oluşturmak ve taşınabilirlik izin veren paralel programları yönetmek kullanıcılara izin verir. Yönergeleri C genişletmek ve C++ sıralı programlama modeli ile tek bir program birden çok veri (SPMD) yapıları, iş paylaşım yapıları ve eşitleme yapıları ve Destek paylaşımı ve veri privatization sağlarlar. OpenMP C ve C++ API desteği derleyicileri etkinleştirir ve tüm OpenMP derleyici yönergeleri yorumu sağlayan derleyici komut satırı seçeneğini dahil edilir.