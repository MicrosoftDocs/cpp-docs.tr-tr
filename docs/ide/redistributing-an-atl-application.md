---
title: "ATL uygulamasını yeniden dağıtma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ATL, redistributing
- redistributing ATL
- redistributing OLE DB templates
- OLE DB templates, redistributing
ms.assetid: 9a696b22-2345-43ec-826b-be7cb8cfd676
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3a9e4259c70aff53252cd91db217a96d9d5480a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="redistributing-an-atl-application"></a>ATL uygulamasını yeniden dağıtma
Visual Studio 2012'den itibaren Etkin Şablon kitaplığı (ATL) yalnızca üstbilgi bir kitaplık değil. ATL projeleri ATL seçeneği için dinamik bir bağlantı yok. Yeniden dağıtılabilir ATL Kitaplık gereklidir.  
  
 ATL çalıştırılabilir uygulamasını yeniden dağıtırsanız, aşağıdaki komutu gönderdikten .exe dosyasına (ve onun içindeki herhangi bir denetim) kaydetmeniz gerekir:  
  
```  
filename /regserver  
```  
  
 Burada `filename` yürütülebilir dosyasının adıdır.  
  
 Visual Studio 2010'da ATL projesinde MinDependency veya MinSize yapılandırması için oluşturulabilir. MinDependency yapılandırması ayarladığınızda aldığınızdır **Kullan'in ATL** özelliğine **statik bağlantı** üzerinde **genel** özellik sayfası ve kümesi  **Çalışma Zamanı Kitaplığı** özelliğine **çok iş parçacıklı (/ MT)** üzerinde **kod oluşturma** özellik sayfası (C/C++ klasörü).  
  
 MinSize yapılandırması ayarladığınızda aldığınızdır **Kullan'in ATL** özelliğine **dinamik bağlantı** üzerinde **genel** özellik sayfası veya kümesi **çalışma zamanı Kitaplık** özelliğine **çok iş parçacıklı DLL (/ MD)** üzerinde **kod oluşturma** özellik sayfası (C/C++ klasörü).  
  
 MinSize çıkış olası ancak gerektiren olabildiğince küçük yapar ATL100.dll ve Msvcr100.dll (seçtiyseniz **çok iş parçacıklı DLL (/ MD)** seçeneği) hedef bilgisayar üzerinde. ATL100.dll tüm ATL işlevselliği mevcut olduğundan emin olmak için hedef bilgisayarda kayıtlı olmalıdır. ANSI ATL100.dll içerir ve Unicode aktarır.  
  
 ATL veya OLE DB Şablonları projenizi MinDependency hedef için yapılandırdıysanız, daha büyük bir program resim alabilirsiniz olsa da, yüklemeniz ve hedef bilgisayarda ATL100.dll kaydetmeniz gerekmez.  
  
 ATL çalıştırılabilir uygulamasını yeniden dağıtırsanız, aşağıdaki komutu gönderdikten .exe dosyasına (ve onun içindeki herhangi bir denetim) kaydetmeniz gerekir:  
  
```  
filename /regserver  
```  
  
 Burada `filename` yürütülebilir dosyasının adıdır.  
  
 OLE DB Şablonları uygulamaları için hedef bilgisayarda Microsoft Data Access Components (MDAC) dosyaların en son sürümlerini olduğundan emin olun. Daha fazla bilgi için bkz: [veritabanı destek dosyalarını yeniden dağıtma](../ide/redistributing-database-support-files.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ Dosyalarını Yeniden Dağıtma](../ide/redistributing-visual-cpp-files.md)