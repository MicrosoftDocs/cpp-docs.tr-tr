---
title: Derleyici Hatası C2338
ms.date: 11/04/2016
f1_keywords:
- C2338
helpviewer_keywords:
- C2338
ms.assetid: 49bba575-1de4-4963-86c6-ce3226a2ba51
ms.openlocfilehash: 4ca3feb2a71efa60229afdbf918109a5d5d59cad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539600"
---
# <a name="compiler-error-c2338"></a>Derleyici Hatası C2338

> *hata iletisi*

Bu hataya neden olabilir bir `static_assert` derleme sırasında hata oluştu. İleti tarafından sağlanan `static_assert` parametreleri.

Bu hata iletisi, dış sağlayıcıları için derleyici tarafından da oluşturulabilir. Çoğu durumda, bu hata, bir öznitelik sağlayıcısı ATLPROV gibi DLL tarafından raporlanır. Bu iletinin bazı ortak biçimleri şunlardır:

> '*özniteliği*' Atl özniteliği sağlayıcısı: hata ATL*numarası* *iletisi*

> Öznitelik yanlış kullanımı '*özniteliği*'

> '*kullanım*': 'kullanımı' özniteliği için yanlış biçim

Bu hatalar genellikle kurtarılamaz olarak kabul edilir ve önemli bir derleyici hatası tarafından izlenebilir.

Bu sorunları düzeltmek için öznitelik kullanımı düzeltin. Örneğin, kullanılabilmesi için önce bazı durumlarda, öznitelik parametreleri bildirilmesi gerekir. Bir ATL hata numarası sağlanmazsa, daha fazla bilgi için hata belgelerine bakın.
