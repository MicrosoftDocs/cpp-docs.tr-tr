---
title: NMAKE önemli hatası U1035 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1035
dev_langs:
- C++
helpviewer_keywords:
- U1035
ms.assetid: 68f0cc59-007e-4109-ac30-7ac4ac447e6d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0383bf4742d637d669070efa5370ebda0c7ab159
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019867"
---
# <a name="nmake-fatal-error-u1035"></a>NMAKE Önemli Hatası U1035

sözdizimi hatası: beklenen ':' veya '=' ayracı

Her iki iki nokta (**:**) ya da eşittir işaretini (**=**) bekleniyordu.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için

1. Bir iki nokta üst üste bir hedef izleyin değil.

1. Tek harfli hedef ardından, bir virgül ve boşluk (örneğin, c:). NMAKE sürücü belirtimi olarak yorumlanır.

1. Bir iki nokta üst üste çıkarım kuralı izleyin değil.

1. Makro tanımı, bir eşittir işareti izlenmeyen.

1. Bir karakteri ve ardından bir eğik çizgi (**\\**) yeni bir satır komutuna devam etmek için kullanıldı.

1. NMAKE söz dizimi kuralların izleyin değil, bir dize görüntülenmektedir.

1. Derleme görevleri dosyası bir sözcük işlemcisi tarafından biçimlendirildi.