---
title: Derleyici hatası C2919
ms.date: 11/04/2016
f1_keywords:
- C2919
helpviewer_keywords:
- C2919
ms.assetid: 140a6db9-eb48-4c5e-84a7-a09d2653605b
ms.openlocfilehash: 624b3ab47ccb1c934b612ec8648b5eee0d233690
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80176981"
---
# <a name="compiler-error-c2919"></a>Derleyici hatası C2919

' Type ': Işleçler bir WinRT türünün yayımlanmış yüzeyinde kullanılamaz

Windows Çalışma Zamanı tür sistemi, bir türün yayınlanan yüzeyinde işleç üye işlevlerini desteklemez. Bunun nedeni, tüm dillerin işleç üye işlevlerini tüketebileceği değildir. Aynı sınıf veya derleme birimi içindeki C++ koddan çağrılabilen özel veya iç işleç üye işlevleri oluşturabilirsiniz.

Bu sorunu onarmak için, işleç üye işlevini ortak arabirimden kaldırın veya adlandırılmış bir üye işlevi ile değiştirin. Örneğin, `operator==`yerine üye işlevi `Equals`olarak adlandırın.
