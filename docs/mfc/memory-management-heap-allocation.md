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
ms.openlocfilehash: d7ef166201103b1544d0a36d82452b485af75418
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928615"
---
# <a name="memory-management-heap-allocation"></a>Bellek Yönetimi: Öbek Ayırma
Yığın bellek ayırma gereksinimlerine program için ayrılmıştır. Program kodunu ve yığını dışında bir alandır. Tipik C programları işlevleri kullanmak **malloc** ve **ücretsiz** ayırmak ve yığın bellek ayırması için. MFC hata ayıklama sürümü C++ yerleşik işleçleri değiştirilmiş sürümlerini sağlar **yeni** ve **silmek** ayrılamadı ve yığın bellek nesneleri serbest bırakma.  
  
 Kullandığınızda **yeni** ve **silmek** yerine **malloc** ve **ücretsiz**, sınıf kitaplığının yararlanmak için bellek sızıntıları algılama yararlı olabilecek bellek yönetimi hata ayıklama geliştirmeler. MFC, standart sürümleri sürümünü programınızla oluşturduğunuzda **yeni** ve **silmek** işleçleri ayırmak ve bellek (sürümünü MFC ayırması için etkili bir yol sağlayın Bu işleçlere değiştirilmiş sürümlerini sağlamaz).  
  
 Toplam boyutu yığında ayrılmış nesneleri, yalnızca, sisteminizin kullanılabilir sanal bellek tarafından sınırlı olduğunu unutmayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bellek Yönetimi](../mfc/memory-management.md)

