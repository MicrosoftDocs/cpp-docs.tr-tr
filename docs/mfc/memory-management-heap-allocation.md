---
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
ms.openlocfilehash: 1f0b07a0a3439faba71078af1e2d7d1559a42b41
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626293"
---
# <a name="memory-management-heap-allocation"></a>Bellek Yönetimi: Öbek Ayırma

Yığın, programın bellek ayırma ihtiyaçları için ayrılmıştır. Program kodundan ve yığından ayrı bir alandır. Tipik C programları, yığın belleğini ayırmak ve **serbest** bırakmak için **malloc** ve ücretsiz işlevlerini kullanır. MFC 'nin hata ayıklama sürümü, C++ yerleşik işleçleri 'nin değiştirilmiş sürümlerini sağlar ve yığın bellekte nesneleri **ayırmak ve serbest** bırakmak için **silin** .

**Malloc** ve **ücretsiz**yerine **New** ve **Delete** kullandığınızda, sınıf kitaplığının bellek yönetimi hata ayıklama geliştirmelerinden faydalanabilir ve bu da bellek sızıntılarını algılamayla yararlı olabilir. Programınızı MFC 'nin yayın sürümüyle yapılandırdığınızda, **Yeni** ve **silme** işleçlerinin standart sürümleri belleği ayırmak ve serbest bırakmak için etkili bır yol sağlar (MFC 'nin yayın sürümü Bu işleçlerin değiştirilen sürümlerini sağlamaz).

Yığında ayrılan nesnelerin toplam boyutunun yalnızca sisteminizin kullanılabilir sanal belleği ile sınırlı olduğunu unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[Bellek yönetimi](memory-management.md)
