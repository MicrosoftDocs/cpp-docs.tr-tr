---
title: "Bellek Yönetimi: Yığın ayırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a8be6dabf4eaae1c76ebe31c35ad5b7b30743953
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="memory-management-heap-allocation"></a>Bellek Yönetimi: Öbek Ayırma
Yığın bellek ayırma gereksinimlerine program için ayrılmıştır. Program kodunu ve yığını dışında bir alandır. Tipik C programları işlevleri kullanmak `malloc` ve **ücretsiz** ayırmak ve yığın bellek ayırması için. MFC hata ayıklama sürümü C++ yerleşik işleçleri değiştirilmiş sürümlerini sağlar **yeni** ve **silmek** ayrılamadı ve yığın bellek nesneleri serbest bırakma.  
  
 Kullandığınızda **yeni** ve **silmek** yerine `malloc` ve **ücretsiz**, sınıf kitaplığının bellek yönetimi hata ayıklama geliştirmeleri avantajlarından yararlanmak için , hangi bellek sızıntılarını algılama yararlı olabilir. MFC, standart sürümleri sürümünü programınızla oluşturduğunuzda **yeni** ve **silmek** işleçleri ayırmak ve bellek (sürümünü MFC ayırması için etkili bir yol sağlayın Bu işleçlere değiştirilmiş sürümlerini sağlamaz).  
  
 Toplam boyutu yığında ayrılmış nesneleri, yalnızca, sisteminizin kullanılabilir sanal bellek tarafından sınırlı olduğunu unutmayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bellek yönetimi](../mfc/memory-management.md)

