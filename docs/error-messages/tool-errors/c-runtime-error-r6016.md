---
title: C Çalışma Zamanı Hatası R6016
ms.date: 11/04/2016
f1_keywords:
- R6016
helpviewer_keywords:
- R6016
ms.assetid: 7bd3f274-d9c4-4bc4-8252-80bf168c4c3a
ms.openlocfilehash: 22bf4b7e8951215d1a013edb29af1ebff7517ffc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80197346"
---
# <a name="c-runtime-error-r6016"></a>C Çalışma Zamanı Hatası R6016

iş parçacığının verileri için yeterli alan yok

> [!NOTE]
> Bir uygulamayı çalıştırırken bu hata iletisiyle karşılaşırsanız, bir iç bellek sorunu olduğundan uygulama kapatıldı. Bu hatanın pek çok nedeni olabilir, ancak genellikle son derece düşük bellek koşulunun, uygulamadaki bir hatanın veya uygulama tarafından kullanılan bir eklenti ya da uzantıdaki bir hata nedeniyle oluşur.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Çalışan diğer uygulamaları kapatın veya belleği boşaltmak için bilgisayarınızı yeniden başlatın.
> - Uygulamayı onarmak ya da yeniden yüklemek için **Denetim Masası** 'ndaki **uygulamalar ve Özellikler** veya **Programlar ve Özellikler** sayfasını kullanın.
> - Uygulama tarafından kullanılan eklentileri veya uzantıları kaldırmak, onarmak ya da yeniden yüklemek için **Denetim Masası** 'ndaki **uygulamalar ve Özellikler** veya **Programlar ve Özellikler** sayfasını kullanın.
> - Yazılım güncelleştirmeleri için **Denetim Masası** 'ndaki **Windows Update** kontrol edin.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcılar için bilgiler**

Bu hata, programın bir [_beginthread](../../c-runtime-library/reference/beginthread-beginthreadex.md) veya `_beginthreadex` çağrısını tamamlaması için işletim sisteminden yeterli bellek alamadığı veya iş parçacığı yerel depolama alanının `_beginthread` veya `_beginthreadex`tarafından başlatılmamış olması nedeniyle oluşur.

Yeni bir iş parçacığı başlatıldığında, kitaplık iş parçacığı için dahili bir veritabanı oluşturmalıdır. Veritabanı işletim sistemi tarafından sağlanan belleği kullanarak genişletilemezse, iş parçacığı başlatılamaz ve çağrı işlemi durur. Bu işlem tarafından çok fazla iş parçacığı oluşturulduğunda veya iş parçacığı yerel depolama alanı tüketildiğinde gerçekleşebilir.

C çalışma zamanı kitaplığı (CRT) çağıran bir yürütülebilir dosyanın Windows API `CreateThread`yerine iş parçacığı oluşturma için `_beginthreadex` kullanması önerilir. `_beginthreadex`, iş parçacığı yerel depolama alanında çok sayıda CRT işlevi tarafından kullanılan iç statik depolamayı başlatır. İş parçacığı oluşturmak için `CreateThread` kullanıyorsanız CRT, başlatılmış iç statik depolama gerektiren bir CRT işleve bir çağrı yapıldığında R6016 ile işlemi sonlandırabilir.
