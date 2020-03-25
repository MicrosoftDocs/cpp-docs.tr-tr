---
title: Önemli Hata C1905
ms.date: 11/04/2016
f1_keywords:
- C1905
helpviewer_keywords:
- C1905
ms.assetid: fefc6769-477f-45a2-9878-6f0a5f42472c
ms.openlocfilehash: 106dfe8a078047225097686d185a1ba43987ce33
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202637"
---
# <a name="fatal-error-c1905"></a>Önemli Hata C1905

Ön uç ve arka uç uyumlu değil (aynı işlemci hedeflenmelidir)

Bu hata, bir. obj dosyası x86, ARM veya x64 gibi bir işlemciyi hedefleyen, ancak farklı bir işlemciyi hedefleyen bir arka uç (C2. dll) tarafından okunmakta olan bir derleyici ön ucu (C1. dll) tarafından oluşturulduğunda oluşur.

Bu sorunu onarmak için, eşleşen bir ön uç ve arka uç kullandığınızdan emin olun. Bu, Visual Studio 'da oluşturulan projeler için varsayılandır. Bu hata, proje dosyasını düzenlediyseniz ve derleyici araçlarına farklı yollar kullandıysanız meydana gelebilir. Derleyici araçlarının yolunu özellikle belirlediyseniz, Visual Studio yüklemeniz bozuksa Bu hata ortaya çıkabilir. Örneğin, derleyici. dll dosyalarını bir konumdan diğerine kopyalamış olabilirsiniz. Visual Studio 'Yu onarmak veya yeniden yüklemek için Windows Denetim Masası 'ndaki **Programlar ve Özellikler ' i** kullanın.
