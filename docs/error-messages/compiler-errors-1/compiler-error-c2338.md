---
title: Derleyici hatası C2338
ms.date: 11/04/2016
f1_keywords:
- C2338
helpviewer_keywords:
- C2338
ms.assetid: 49bba575-1de4-4963-86c6-ce3226a2ba51
ms.openlocfilehash: c92a95b97cb4c57d3ad5cfbf8fe1d9980d5362cd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221217"
---
# <a name="compiler-error-c2338"></a>Derleyici hatası C2338

> *Hata iletisi*

Bu hata, derleme sırasında oluşan bir **`static_assert`** hatadan kaynaklanabilir. İleti, parametreler tarafından sağlanır **`static_assert`** .

Bu hata iletisi, derleyiciye dış sağlayıcılar tarafından da oluşturulabilir. Çoğu durumda, bu hatalar ATLPROV gibi bir öznitelik sağlayıcısı DLL tarafından raporlanır. Bu iletinin bazı yaygın formları şunlardır:

- '*Attribute*' ATL öznitelik sağlayıcısı: hata ATL*numarası* *iletisi*

- '*Attribute*' özniteliğinin yanlış kullanımı

- '*kullanım*': ' usage ' özniteliği için yanlış biçim

Bu hatalar genellikle kurtarılamaz olur ve sonrasında önemli bir derleyici hatası olabilir.

Bu sorunları gidermek için öznitelik kullanımını düzeltin. Örneğin, bazı durumlarda öznitelik parametrelerinin kullanılabilmesi için önce bildirilmelidir. ATL hata numarası sağlanmışsa, daha ayrıntılı bilgi edinmek için ilgili hataya yönelik belgelere bakın.
