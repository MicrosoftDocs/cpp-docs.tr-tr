---
description: 'Daha fazla bilgi edinin: C çalışma zamanı hatası R6033'
title: C Çalışma Zamanı Hatası R6033
ms.date: 11/04/2016
f1_keywords:
- R6033
helpviewer_keywords:
- R6033
ms.assetid: f9cffdc9-81bd-4a64-a698-02762cbd82c9
ms.openlocfilehash: 377f872957af4ab4a844e7d93345a612a16c0490
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206610"
---
# <a name="c-runtime-error-r6033"></a>C Çalışma Zamanı Hatası R6033

Yerel kod başlatma sırasında bu derlemeden MSIL kodunu kullanmayı deneyin. Bu, uygulamanızdaki bir hatayı gösterir. Büyük olasılıkla, yerel bir oluşturucudan veya DllMain 'den bir MSIL derlenmiş (/CLR) işlevini çağırma sonucudur.

> [!NOTE]
> Bir uygulamayı çalıştırırken bu hata iletisiyle karşılaşırsanız, bir iç sorun olduğundan uygulama kapatıldı. Bu hata, uygulamadaki bir hata ya da bir eklenti veya uzantı içindeki bir hata nedeniyle oluşabilir.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Programı onarmak ya da yeniden yüklemek için **Denetim Masası** 'ndaki **uygulamalar ve Özellikler** veya **Programlar ve Özellikler** sayfasını kullanın.
> - Tüm uzantıları veya eklentileri kaldırmak, onarmak ya da yeniden yüklemek için **Denetim Masası** 'ndaki **uygulamalar ve Özellikler** veya **Programlar ve Özellikler** sayfasını kullanın.
> - Yazılım güncelleştirmeleri için **Denetim Masası** 'ndaki **Windows Update** kontrol edin.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcılar için bilgiler**

Bu tanılama, yükleyici kilidi sırasında MSIL yönergelerinin yürütüldüğü anlamına gelir. Yerel C++ ' ı/clr bayrağını kullanarak derlemişse bu durum oluşabilir. Yalnızca yönetilen kod içeren modüllerde/clr bayrağını kullanın. Daha fazla bilgi için bkz. [karışık derlemeleri başlatma](../../dotnet/initialization-of-mixed-assemblies.md).
