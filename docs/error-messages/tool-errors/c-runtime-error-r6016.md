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
ms.openlocfilehash: f366ceff24ce65e6f7869f9709f547651687c327
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33306942"
---
# <a name="c-runtime-error-r6016"></a>C çalışma zamanı hatası R6016
iş parçacığının verileri için yeterli alan yok  
  
> [!NOTE]
>  Bir uygulama çalıştırırken bu hata iletisi alırsanız, bir iç bellek sorunu olduğundan uygulama kapatıldı. Bu hatanın birçok olası nedeni vardır, ancak genellikle, uygulama hatada bir son derece düşük bellek koşula göre veya eklenti veya uygulama tarafından kullanılan uzantısı bir hatadan kaynaklanır.  
>   
>  Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:  
>   
>  -   Çalışan diğer uygulamaları kapatın veya belleği boşaltmak için bilgisayarınızı yeniden başlatın.  
> -   Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasındaki **Denetim Masası** onarın veya uygulamayı yeniden yükleyin.  
> -   Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasındaki **Denetim Masası** kaldırmayı, onarın veya eklentileri veya uygulama tarafından kullanılan uzantıları yeniden yükleyin.  
> -   Denetleme **Windows Update** içinde **Denetim Masası** yazılım güncelleştirmeleri için.  
> -   Uygulamanın güncelleştirilmiş bir sürümünü denetle. Sorun devam ederse uygulamanın satıcısına başvurun.  
  
 **Programcıları için bilgi**  
  
 Program işletim sistemini tamamlamak için yeterli bellek almadığından bu hata oluşur. bir [_beginthread](../../c-runtime-library/reference/beginthread-beginthreadex.md) veya `_beginthreadex` çağrısı veya iş parçacığı yerel depolaması tarafından başlatılmadı `_beginthread` veya `_beginthreadex`.  
  
 Yeni bir iş parçacığı başlatıldığında, kitaplık iş parçacığı için dahili bir veritabanı oluşturmalıdır. Veritabanı işletim sistemi tarafından sağlanan belleği kullanarak genişletilemezse, iş parçacığı başlatılamaz ve çağrı işlemi durur. Bu işlem tarafından çok fazla iş parçacığı oluşturulduğunda veya iş parçacığı yerel depolama alanı tüketildiğinde gerçekleşebilir.  
  
 C çalışma zamanı kitaplığı (CRT) çağıran bir yürütülebilir dosya kullanması gereken öneririz `_beginthreadex` Windows API yerine iş parçacığı oluşturma için `CreateThread`. `_beginthreadex` iş parçacığı yerel depolaması birçok CRT işlevleri tarafından kullanılan iç statik depolama başlatır. Kullanırsanız `CreateThread` başlatılmış dahili statik depolama gerektiren bir CRT işlevi çağrısı yapıldığında, bir iş parçacığı oluşturmak için CRT R6016 işlemine sonlandırabilir.