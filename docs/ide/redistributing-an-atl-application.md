---
title: ATL uygulamasını yeniden dağıtma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ATL, redistributing
- redistributing ATL
- redistributing OLE DB templates
- OLE DB templates, redistributing
ms.assetid: 9a696b22-2345-43ec-826b-be7cb8cfd676
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5c824dd4ae174a4418c6744e592dd62dc54b9595
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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