---
title: Derleyici Hatası C2919
ms.date: 11/04/2016
f1_keywords:
- C2919
helpviewer_keywords:
- C2919
ms.assetid: 140a6db9-eb48-4c5e-84a7-a09d2653605b
ms.openlocfilehash: ab11226c8cc4629a265dd182d5f882f6b3be7e5d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160865"
---
# <a name="compiler-error-c2919"></a>Derleyici Hatası C2919

'type': İşleçler bir WinRT türünün yayımlanmış yüzeyinde kullanılamaz

Windows çalışma zamanı tür sistemi türünün yayımlanmış yüzeyinde işleci üye işlevlerini desteklemez. Tüm diller, işleç üye işlevleri tüketebildiğinden budur. Aynı sınıf ya da derleme biriminde C++ koddan çağrılabilir üye işlevleri, özel veya iç işleci oluşturabilirsiniz.

Bu sorunu gidermek için işleç üye işlevini ortak arabirimden kaldırın veya adlandırılmış üyesinin işleve değiştirin. Örneğin, yerine, `operator==`, üye işlev adı `Equals`.