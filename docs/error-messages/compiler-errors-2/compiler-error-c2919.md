---
title: Derleyici Hatası C2919 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2919
dev_langs:
- C++
helpviewer_keywords:
- C2919
ms.assetid: 140a6db9-eb48-4c5e-84a7-a09d2653605b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5d6ee01e32cd1855855fa6ac071af159be8bac0d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106837"
---
# <a name="compiler-error-c2919"></a>Derleyici Hatası C2919

'type': işleçler bir WinRT türünün yayımlanmış yüzeyinde kullanılamaz

Windows çalışma zamanı tür sistemi türünün yayımlanmış yüzeyinde işleci üye işlevlerini desteklemez. Tüm diller, işleç üye işlevleri tüketebildiğinden budur. Aynı sınıf ya da derleme biriminde C++ koddan çağrılabilir üye işlevleri, özel veya iç işleci oluşturabilirsiniz.

Bu sorunu gidermek için işleç üye işlevini ortak arabirimden kaldırın veya adlandırılmış üyesinin işleve değiştirin. Örneğin, yerine, `operator==`, üye işlev adı `Equals`.