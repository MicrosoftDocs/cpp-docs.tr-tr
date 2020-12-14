---
description: 'Daha fazla bilgi edinin: C çalışma zamanı hatası R6016'
title: C Çalışma Zamanı Hatası R6016
ms.date: 11/04/2016
f1_keywords:
- R6016
helpviewer_keywords:
- R6016
ms.assetid: 7bd3f274-d9c4-4bc4-8252-80bf168c4c3a
ms.openlocfilehash: 79339400436f21aefc0edea101b4642d443f5ce0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237692"
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

Bu hata, programın bir [_beginthread](../../c-runtime-library/reference/beginthread-beginthreadex.md) veya çağrıyı tamamlaması için işletim sisteminden yeterli bellek almadığı `_beginthreadex` veya iş parçacığı yerel depolama alanının veya tarafından başlatılmamış olması nedeniyle oluşur `_beginthread` `_beginthreadex` .

Yeni bir iş parçacığı başlatıldığında, kitaplık iş parçacığı için dahili bir veritabanı oluşturmalıdır. Veritabanı işletim sistemi tarafından sağlanan belleği kullanarak genişletilemezse, iş parçacığı başlatılamaz ve çağrı işlemi durur. Bu işlem tarafından çok fazla iş parçacığı oluşturulduğunda veya iş parçacığı yerel depolama alanı tüketildiğinde gerçekleşebilir.

C çalışma zamanı kitaplığı (CRT) çağıran bir yürütülebilir dosyanın `_beginthreadex` WINDOWS API yerine iş parçacığı oluşturma için kullanılması gerektiğini öneririz `CreateThread` . `_beginthreadex` iş parçacığı yerel depolama alanında çok sayıda CRT işlevi tarafından kullanılan iç statik depolamayı başlatır. `CreateThread`Bir iş parçacığı oluşturmak için KULLANıYORSANıZ CRT, başlatılan iç statik depolama gerektiren BIR CRT işlevine yapılan bir çağrı yapıldığında R6016 ile işlemi sonlandırabilir.
