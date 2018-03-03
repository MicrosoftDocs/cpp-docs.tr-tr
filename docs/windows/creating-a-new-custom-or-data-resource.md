---
title: "Yeni özel veya veri kaynağı oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.binary
dev_langs:
- C++
helpviewer_keywords:
- custom resources [C++]
- data resources [C++]
- resources [Visual Studio], creating
ms.assetid: 9918bf96-38fa-43a1-a384-572f95d84950
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eb376bd640c5b56bfbe5a855f0df91a9a0cb6b7a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-new-custom-or-data-resource"></a>Yeni Özel veya Veri Kaynağı Oluşturma
Yeni bir özel veya veri kaynağı kaynak normal kaynak komut dosyası (.rc) dosya sözdizimi kullanılarak ayrı bir dosyada ve bu dosyayı dahil Çözüm Gezgini'nde projenize sağ tıklatıp koyarak oluşturabileceğiniz **kaynak içerir**  kısayol menüsünde.  
  
### <a name="to-create-a-new-custom-or-data-resource"></a>Yeni bir özel veya veri kaynağı oluşturmak için  
  
1. [.Rc dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md) özel veya veri kaynağı içeriyor.  
  
     Null ile sonlandırılmış tırnak içine alınmış dizeler veya ondalık, onaltılık veya sekizlik biçiminde tamsayı olarak .rc dosyasında özel veri türü.  
  
2.  İçinde **Çözüm Gezgini**, projenizin .rc dosyasını sağ tıklatın ve ardından **kaynağını içeren** kısayol menüsünde.  
  
3.  İçinde **derleme zamanı yönergeleri** kutusuna bir **#include** özel kaynağınızın içeren dosyanın adını veren ifade. Örneğin:  
  
 ```  
    #include mydata.rc  
 ```  
  
     Sözdizimi ve ne tür, yazım doğru olduğundan emin olun. İçeriğini **derleme zamanı yönergeleri** kutusuna yazdığınız tam olarak kaynak betik dosyasına eklenir.  
  
4.  Tıklatın **Tamam** yaptığınız değişiklikleri kaydetmek için.  
  
 Özel bir kaynak oluşturmak için başka bir harici dosya özel kaynak olarak almak için yoludur. Daha fazla bilgi için bkz: [alma ve verme kaynakları](../windows/how-to-import-and-export-resources.md).  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
 Gereksinimler  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İkili Düzenleyicisi](binary-editor.md)

