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
ms.openlocfilehash: 4ce963d312d145e26567a5902f32e45735eb1d89
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438424"
---
# <a name="1-introduction"></a>1. Giriş

Bu belge, derleyici yönergeleri, kitaplık işlevleri ve paylaşılan bellek paralellik C ve C++ programlarında belirtmek için kullanılan ortam değişkenleri koleksiyonu belirtir. Bu belgede açıklanan işlevselliğini toplu olarak bilinen *OpenMP C/C++ uygulama programı arabirimi (API)*. Bu belirtim paralel, programlama için bir model sağlamak için bir program, farklı satıcıların paylaşılan bellek mimariler arasında taşınabilir olarak tanır hedefidir. OpenMP C/C++ API, çok sayıda satıcılardan derleyiciler tarafından desteklenecektir. OpenMP hakkında daha fazla bilgi dahil olmak üzere *OpenMP Fortran uygulaması Program arabirimi*, aşağıdaki web sitesinde bulunabilir:

[http://www.openmp.org](http://www.openmp.org)

Yönergeleri, kitaplık işlevleri ve bu belgede tanımlanan ortam değişkenleri oluşturma ve paralel programlar taşınabilirlik erişimine izin verme yönetme olanağı sağlar. Yönergeleri C genişletmek ve C++ sıralı programlama modeli ile tek bir programda birden çok (SPMD) veri yapıları, iş paylaşım yapıları ve eşitleme yapılarını ve Paylaşım ve veri privatization desteği sağlar. OpenMP C ve C++ API destekleyen derleyiciler etkinleştirir ve tüm OpenMP derleyici yönergeleri yorumu sağlayan derleyici komut satırı seçeneğini dahil edilir.