---
title: 1. Giriş
ms.date: 11/04/2016
ms.assetid: c42e72bc-0e31-4b1c-b670-cd82673c0c5a
ms.openlocfilehash: b365ff828fd7dc2b7d9d3136a4fbfb68c43902ce
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50554719"
---
# <a name="1-introduction"></a>1. Giriş

Bu belge, derleyici yönergeleri, kitaplık işlevleri ve paylaşılan bellek paralellik C ve C++ programlarında belirtmek için kullanılan ortam değişkenleri koleksiyonu belirtir. Bu belgede açıklanan işlevselliğini toplu olarak bilinen *OpenMP C/C++ uygulama programı arabirimi (API)*. Bu belirtim paralel, programlama için bir model sağlamak için bir program, farklı satıcıların paylaşılan bellek mimariler arasında taşınabilir olarak tanır hedefidir. OpenMP C/C++ API, çok sayıda satıcılardan derleyiciler tarafından desteklenecektir. OpenMP hakkında daha fazla bilgi dahil olmak üzere *OpenMP Fortran uygulaması Program arabirimi*, aşağıdaki web sitesinde bulunabilir:

[http://www.openmp.org](http://www.openmp.org)

Yönergeleri, kitaplık işlevleri ve bu belgede tanımlanan ortam değişkenleri oluşturma ve paralel programlar taşınabilirlik erişimine izin verme yönetme olanağı sağlar. Yönergeleri C genişletmek ve C++ sıralı programlama modeli ile tek bir programda birden çok (SPMD) veri yapıları, iş paylaşım yapıları ve eşitleme yapılarını ve Paylaşım ve veri privatization desteği sağlar. OpenMP C ve C++ API destekleyen derleyiciler etkinleştirir ve tüm OpenMP derleyici yönergeleri yorumu sağlayan derleyici komut satırı seçeneğini dahil edilir.