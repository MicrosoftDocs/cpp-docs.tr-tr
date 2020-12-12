---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2919'
title: Derleyici hatası C2919
ms.date: 11/04/2016
f1_keywords:
- C2919
helpviewer_keywords:
- C2919
ms.assetid: 140a6db9-eb48-4c5e-84a7-a09d2653605b
ms.openlocfilehash: 0e6498961fc5000897bcd9815c3cd3a6f90ecdfb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270348"
---
# <a name="compiler-error-c2919"></a>Derleyici hatası C2919

' Type ': Işleçler bir WinRT türünün yayımlanmış yüzeyinde kullanılamaz

Windows Çalışma Zamanı tür sistemi, bir türün yayınlanan yüzeyinde işleç üye işlevlerini desteklemez. Bunun nedeni, tüm dillerin işleç üye işlevlerini tüketebileceği değildir. Aynı sınıf veya derleme birimi içindeki C++ kodundan çağrılabilen özel veya iç işleç üye işlevleri oluşturabilirsiniz.

Bu sorunu onarmak için, işleç üye işlevini ortak arabirimden kaldırın veya adlandırılmış bir üye işlevi ile değiştirin. Örneğin, yerine `operator==` üye işlevini adlandırın `Equals` .
