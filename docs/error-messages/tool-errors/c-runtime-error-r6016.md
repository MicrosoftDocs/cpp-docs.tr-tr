---
title: "C çalışma zamanı hatası R6016 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- R6016
dev_langs:
- C++
helpviewer_keywords:
- R6016
ms.assetid: 7bd3f274-d9c4-4bc4-8252-80bf168c4c3a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 451ff01b201b110ac5f05140e3b8581f1a8c2e28
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
  
 C çalışma zamanı kitaplığı (CRT) çağıran bir yürütülebilir dosya kullanması gereken öneririz `_beginthreadex` Windows API yerine iş parçacığı oluşturma için `CreateThread`. `_beginthreadex`iş parçacığı yerel depolaması birçok CRT işlevleri tarafından kullanılan iç statik depolama başlatır. Kullanırsanız `CreateThread` başlatılmış dahili statik depolama gerektiren bir CRT işlevi çağrısı yapıldığında, bir iş parçacığı oluşturmak için CRT R6016 işlemine sonlandırabilir.