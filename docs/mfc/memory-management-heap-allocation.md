---
description: 'Daha fazla bilgi edinin: bellek yönetimi: yığın ayırma'
title: 'Bellek Yönetimi: Öbek Ayırma'
ms.date: 11/04/2016
helpviewer_keywords:
- memory [MFC], detecting leaks
- delete operator [MFC], using with debug MFC
- heap allocation [MFC], described
- memory allocation [MFC], heap memory
- memory leaks [MFC], detecting
- new operator [MFC], using with debug MFC
- heap allocation [MFC]
- detecting memory leaks [MFC]
ms.assetid: a5d949c6-1b79-476e-9c66-513a558203d9
ms.openlocfilehash: bb9035d1346f1d3bbff53a03da9b4cf1d946a7ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259662"
---
# <a name="memory-management-heap-allocation"></a>Bellek Yönetimi: Öbek Ayırma

Yığın, programın bellek ayırma ihtiyaçları için ayrılmıştır. Program kodundan ve yığından ayrı bir alandır. Tipik C programları, yığın belleğini ayırmak ve **serbest** bırakmak için **malloc** ve ücretsiz işlevlerini kullanır. MFC 'nin hata ayıklama sürümü, C++ yerleşik işleçleri 'nin değiştirilmiş sürümlerini sağlar **`new`** ve **`delete`** yığın bellekte nesneleri ayırır ve serbest bırakabilir.

**`new`** Hem **`delete`** **malloc** hem de **ücretsiz** olarak kullandığınızda, sınıf kitaplığının bellek yönetimi hata ayıklama geliştirmelerinden yararlanabilirsiniz. Bu, bellek sızıntılarını algılamayla yararlı olabilir. Programınızı MFC 'nin yayın sürümüyle derlediğinizde, **`new`** ve işleçlerinin standart sürümleri **`delete`** belleği ayırmak ve serbest bırakmak için etkili bir yol sağlar (MFC 'nin yayın sürümü Bu işleçlerin değiştirilen sürümlerini sağlamaz).

Yığında ayrılan nesnelerin toplam boyutunun yalnızca sisteminizin kullanılabilir sanal belleği ile sınırlı olduğunu unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[Bellek yönetimi](memory-management.md)
