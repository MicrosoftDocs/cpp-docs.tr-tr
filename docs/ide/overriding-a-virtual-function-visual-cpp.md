---
title: Bir sanal işlevi geçersiz kılma
ms.date: 11/12/2018
f1_keywords:
- vc.codewiz.virtualfunc.override
helpviewer_keywords:
- virtual functions, overriding
- base classes, overriding virtual functions defined in
- Properties window, overriding virtual functions in
ms.assetid: 2d8c76f2-7a6b-4c9c-8de5-4282ce7755b6
ms.openlocfilehash: 9bb3fd34bbfa14cce1595ed586c4e1b66518e7b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350562"
---
# <a name="override-a-virtual-function"></a>Bir sanal işlevi geçersiz kılma

Visual Studio temel sınıfta tanımlı sanal işlevleri geçersiz kılma [Özellikler penceresi](/visualstudio/ide/reference/properties-window).

**Özellikler penceresinde bir sanal işlevi geçersiz kılmak için:**

1. Sınıf Görünümü'nde sınıfı seçin.

1. Özellikler penceresinde seçin **geçersiz kılmalar** düğmesi.

   > [!NOTE]
   > **Geçersiz kılmalar** düğmesi, sınıf görünümü veya kaynak pencereye seçtiğinizde, sınıf adı seçtiğinizde kullanılabilir.

   Sol sütunda, sanal işlevleri listeler. Sanal bir işlevin adını sağ sütunda da görünüyorsa, bir geçersiz kılma zaten uygulandı.

1. İşlev geçersiz kılma varsa, seçip hücrenin sağ sütunda önerilen işlevin adını görüntülemek için Özellikler penceresindeki geçersiz kılma olarak \<Ekle >*FuncName*.

1. İşlev için saptama kodu eklemek için önerilen adı seçin.

1. Bir geçersiz kılma işlevi düzenlemek için Sınıf Görünümü'nde işlev adına çift tıklayın ve kaynak penceresinde kodu düzenleyin.

Bir geçersiz kılma kaldırmak için sağ sütunda geçersiz kılma işlev adı seçin ve seçin \<sil >*FuncName*. İşlev kod dışı bırakılmıştır.
