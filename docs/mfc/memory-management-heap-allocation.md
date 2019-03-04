---
title: 'Bellek Yönetimi: Yığın ayırma'
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
ms.openlocfilehash: 93eee5cbfe1cd49042a9080f06657e751640de69
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57281180"
---
# <a name="memory-management-heap-allocation"></a>Bellek Yönetimi: Yığın ayırma

Yığın, program bellek ayırma ihtiyaçları için ayrılmıştır. Program kodu ve yığın dışında bir alandır. Tipik C programları işlevleri kullanmak **malloc** ve **ücretsiz** ayırmak ve yığın bellek serbest bırakın. MFC hata ayıklama sürümünü C++ yerleşik işleçler değiştirilmiş sürümlerini sağlar **yeni** ve **Sil** ayırmak ve yığın bellek nesneleri serbest bırakın.

Kullanırken **yeni** ve **Sil** yerine **malloc** ve **ücretsiz**, Sınıf Kitaplığı'nızın yararlanmak için bellek sızıntılarını algılama içinde yararlı olabilecek bellek yönetimi hata ayıklama geliştirmeleri. MFC, standart sürümlerini sürümü ile programınızın oluşturduğunuzda **yeni** ve **Sil** işleçleri ayırma ve serbest bellek (sürümünü MFC için etkili bir yol sağlayın Bu işleçler değiştirilmiş sürümlerini sağlamaz).

Yalnızca sistem kullanılabilir sanal bellek tarafından yığında ayrılan nesnelerin toplam boyutu sınırlı olduğunu unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Yönetimi](../mfc/memory-management.md)
