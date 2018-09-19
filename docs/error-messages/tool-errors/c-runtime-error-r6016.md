---
title: C çalışma zamanı hatası R6016 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6016
dev_langs:
- C++
helpviewer_keywords:
- R6016
ms.assetid: 7bd3f274-d9c4-4bc4-8252-80bf168c4c3a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 65f4b4529e0faf433ff9dc5c4fc2c0594a4d9ff6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076651"
---
# <a name="c-runtime-error-r6016"></a>C çalışma zamanı hatası R6016

iş parçacığının verileri için yeterli alan yok

> [!NOTE]
>  Bir uygulama çalıştırırken bu hatayla karşılaşırsanız, dahili bellek sorunu olduğundan uygulaması kapatıldı. Bu hata birçok olası nedenleri vardır, ancak bir son derece düşük bellek durumu, uygulamada, bir hata veya bir hatayı bir eklenti veya uygulama tarafından kullanılan uzantısı tarafından genellikle neden olur.
>
>  Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
>  -   Çalışan diğer uygulamaları kapatın veya belleği boşaltmak için bilgisayarınızı yeniden başlatın.
> -   Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** uygulamayı yeniden yükleyin veya onarın.
> -   Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** kaldırmak onarın veya eklentiler veya uygulama tarafından kullanılan uzantıları yeniden yükleyin.
> -   Denetleme **Windows Update** içinde **Denetim Masası** yazılım güncelleştirmeleri için.
> -   Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcıları için bilgi**

Programın işletim sisteminden tamamlamak için yeterli bellek almadığı için bu hata oluşur. bir [_beginthread](../../c-runtime-library/reference/beginthread-beginthreadex.md) veya `_beginthreadex` araması ya da iş parçacığı yerel depolama ile başlatılmamış `_beginthread` veya `_beginthreadex`.

Yeni bir iş parçacığı başlatıldığında, kitaplık iş parçacığı için dahili bir veritabanı oluşturmalıdır. Veritabanı işletim sistemi tarafından sağlanan belleği kullanarak genişletilemezse, iş parçacığı başlatılamaz ve çağrı işlemi durur. Bu işlem tarafından çok fazla iş parçacığı oluşturulduğunda veya iş parçacığı yerel depolama alanı tüketildiğinde gerçekleşebilir.

C çalışma zamanı kitaplığı (CRT) çağıran yürütülebilir dosyanın kullanmasını öneririz `_beginthreadex` Windows API yerine iş parçacığı oluşturmak için `CreateThread`. `_beginthreadex` iş parçacığı yerel depolama alanındaki pek çok CRT işlevi tarafından kullanılan dahili statik depolama alanını başlatır. Kullanırsanız `CreateThread` başlatılmış statik depolama alanı gerektiren bir CRT işlevini çağrı yapıldığında, bir iş parçacığı oluşturmak için CRT işlemi R6016 ile sonlandırabilir.