---
title: Önemli hata C1061
ms.date: 11/04/2016
f1_keywords:
- C1061
helpviewer_keywords:
- C1061
ms.assetid: 9366c0bc-96e0-4967-aa7d-4ebf098de806
ms.openlocfilehash: 1733a13e697af775653609ddfcc22f7297dad240
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363966"
---
# <a name="fatal-error-c1061"></a>Önemli hata C1061

derleyici sınırı: bloklar çok derin şekilde iç içe geçmiş

Kod bloklarının iç içe geçmesi, 128 iç içe geçme düzeyini aşıyor. Bu, hem 32-bit hem de 64-bit araç kümesinde C ve C++için derleyicideki kesin sınırdır. İç içe geçme düzeylerinin sayısı, bir kapsam ya da blok oluşturan herhangi bir şey tarafından artırılabilir. Örneğin, ad alanları, kullanma yönergeleri, önişlemci genişletmeleri, şablon genişletme, özel durum işleme, döngü yapıları ve else-if yan tümceleri tüm derleyici tarafından görülen iç içe geçme düzeyini artırabilir.

Bu hatayı düzeltmek için kodunuzu yeniden düzenlemelisiniz. Her durumda, derin bir biçimde iç içe geçmiş kodu anlamak zordur. Kodunuzu daha az iç içe geçme düzeyine sahip olacak şekilde yeniden düzenlemeniz, kodunuzun kalitesini artırabilir ve bakımı kolaylaştırabilir. Derin bir biçimde iç içe geçmiş kodu, orijinal içerikten çağrılan işlevlere ayırın. Bir blok içindeki döngü sayısını veya zincirli else-if yan tümcelerinin sayısını sınırlayın.