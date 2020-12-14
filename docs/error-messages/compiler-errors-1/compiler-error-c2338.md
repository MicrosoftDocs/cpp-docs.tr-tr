---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2338'
title: Derleyici hatası C2338
ms.date: 11/04/2016
f1_keywords:
- C2338
helpviewer_keywords:
- C2338
ms.assetid: 49bba575-1de4-4963-86c6-ce3226a2ba51
ms.openlocfilehash: 7bbbc7fd6240fce2def470a0d16aa0dba152a109
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234806"
---
# <a name="compiler-error-c2338"></a>Derleyici hatası C2338

> *Hata iletisi*

Bu hata, derleme sırasında oluşan bir **`static_assert`** hatadan kaynaklanabilir. İleti, parametreler tarafından sağlanır **`static_assert`** .

Bu hata iletisi, derleyiciye dış sağlayıcılar tarafından da oluşturulabilir. Çoğu durumda, bu hatalar ATLPROV gibi bir öznitelik sağlayıcısı DLL tarafından raporlanır. Bu iletinin bazı yaygın formları şunlardır:

- '*Attribute*' ATL öznitelik sağlayıcısı: hata ATL *numarası* *iletisi*

- '*Attribute*' özniteliğinin yanlış kullanımı

- '*kullanım*': ' usage ' özniteliği için yanlış biçim

Bu hatalar genellikle kurtarılamaz olur ve sonrasında önemli bir derleyici hatası olabilir.

Bu sorunları gidermek için öznitelik kullanımını düzeltin. Örneğin, bazı durumlarda öznitelik parametrelerinin kullanılabilmesi için önce bildirilmelidir. ATL hata numarası sağlanmışsa, daha ayrıntılı bilgi edinmek için ilgili hataya yönelik belgelere bakın.
