---
title: 'Bellek Yönetimi: Yığın ayırma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cc158ceda21bfb04053bbc490a3333a76e2d7afe
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383824"
---
# <a name="memory-management-heap-allocation"></a>Bellek Yönetimi: Öbek Ayırma

Yığın, program bellek ayırma ihtiyaçları için ayrılmıştır. Program kodu ve yığın dışında bir alandır. Tipik C programları işlevleri kullanmak **malloc** ve **ücretsiz** ayırmak ve yığın bellek serbest bırakın. MFC hata ayıklama sürümünü C++ yerleşik işleçler değiştirilmiş sürümlerini sağlar **yeni** ve **Sil** ayırmak ve yığın bellek nesneleri serbest bırakın.

Kullanırken **yeni** ve **Sil** yerine **malloc** ve **ücretsiz**, Sınıf Kitaplığı'nızın yararlanmak için bellek sızıntılarını algılama içinde yararlı olabilecek bellek yönetimi hata ayıklama geliştirmeleri. MFC, standart sürümlerini sürümü ile programınızın oluşturduğunuzda **yeni** ve **Sil** işleçleri ayırma ve serbest bellek (sürümünü MFC için etkili bir yol sağlayın Bu işleçler değiştirilmiş sürümlerini sağlamaz).

Yalnızca sistem kullanılabilir sanal bellek tarafından yığında ayrılan nesnelerin toplam boyutu sınırlı olduğunu unutmayın.

## <a name="see-also"></a>Ayrıca Bkz.

[Bellek Yönetimi](../mfc/memory-management.md)

