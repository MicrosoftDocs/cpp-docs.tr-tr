---
title: C Çalışma Zamanı Hatası R6033
ms.date: 11/04/2016
f1_keywords:
- R6033
helpviewer_keywords:
- R6033
ms.assetid: f9cffdc9-81bd-4a64-a698-02762cbd82c9
ms.openlocfilehash: 86ac98a2635975b811c7b50020e4d4782675ae4d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80197023"
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

Bu tanılama, yükleyici kilidi sırasında MSIL yönergelerinin yürütüldüğü anlamına gelir. /Clr bayrağını kullanarak yerel C++ olarak derlenen bu durum oluşabilir. Yalnızca yönetilen kod içeren modüllerde/clr bayrağını kullanın. Daha fazla bilgi için bkz. [karışık derlemeleri başlatma](../../dotnet/initialization-of-mixed-assemblies.md).
