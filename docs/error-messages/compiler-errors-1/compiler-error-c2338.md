---
title: Derleyici Hatası C2338 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2338
dev_langs:
- C++
helpviewer_keywords:
- C2338
ms.assetid: 49bba575-1de4-4963-86c6-ce3226a2ba51
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 77bc98afdad36e0505abb58ee06ec1c7e7654ae5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46071581"
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
