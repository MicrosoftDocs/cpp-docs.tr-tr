---
title: "Visual C++ uygulamasını yerel uygulama klasörüne dağıtma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: deploying Visual C++ applications
ms.assetid: 47a81c47-9dbe-47c6-96cc-fbb2fda5e6ad
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1d9a92a5fef96932f1d6a58503fe6355b5a410ce
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-deploying-a-visual-c-application-to-an-application-local-folder"></a>İzlenecek Yol: Visual C++ Uygulamasını Yerel Uygulama Klasörüne Dağıtma
Visual C++ uygulamasını dosyaları klasörüne kopyalayarak dağıtmayı açıklar.  
  
## <a name="prerequisites"></a>Önkoşullar  
  
-   Visual Studio yüklü olan bir bilgisayar.  
  
-   Visual C++ kitaplıkları bulunmayan başka bir bilgisayar.  
  
### <a name="to-deploy-an-application-to-an-application-local-folder"></a>Bir uygulamayı bir yerel uygulama klasörüne dağıtma  
  
1.  Ve MFC uygulaması içindeki adımları izleyerek oluşturmak [izlenecek yol: bir Visual C++ uygulamasını kullanarak bir kurulum projesi dağıtma](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md).  
  
2.  Uygun MFC ve C çalışma zamanı (CRT) kitaplık dosyalarını kopyalayın — Örneğin, bir x86 için platform ve Unicode desteği, kopyalama mfc100u.dll ve msvcr100.dll \Program Visual Studio 10.0\VC\redist\x86\—and öğesinden sonra bunları \Release\ klasöründe yapıştırın MFC projenize. Kopyalamak olabilir diğer dosyalar hakkında daha fazla bilgi için bkz: [belirleme hangi DLL'lerin yeniden dağıtılacağını](../ide/determining-which-dlls-to-redistribute.md).  
  
3.  MFC uygulaması Visual C++ kitaplıkları yok ikinci bir bilgisayarda çalıştırın.  
  
    1.  \Release\ klasörünün içeriğini kopyalayın ve ikinci bilgisayara uygulama klasöründe yapıştırabilirsiniz.  
  
    2.  Uygulamayı ikinci bilgisayarda çalıştırın.  
  
     Visual C++ kitaplıkları yerel uygulama klasöründe kullanılabilir olmadığından uygulama başarıyla çalışır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dağıtım Örnekleri](../ide/deployment-examples.md)