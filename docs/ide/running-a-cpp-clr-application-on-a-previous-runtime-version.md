---
title: "Önceki bir çalışma zamanı sürümünde C++ - clr uygulaması çalıştırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- applications [C++], runtime version specified
- versions [C++]
- app.config files, runtime version specified
- compatibility [C++], runtime version specified
- backward compatibility [C++], runtime version specified
- application deployment [C++], runtime version specified
- common language runtime [C++], version specified
- deploying applications [C++], runtime version specified
ms.assetid: 940171b7-6937-4b14-8e87-c199e23f4f2e
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1f64c0dc31be260332d4d79e8fa38d63bbf6357c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="running-a-c-clr-application-on-a-previous-runtime-version"></a>Önceki Çalışma Zamanı Sürümünde C++ /clr Uygulaması Çalıştırma
Aksi belirtilmediği sürece, C++ .NET Framework uygulama derleyici uygulamayı oluşturmak için kullandığı ortak dil çalışma zamanı (CLR) sürümünde çalıştırmak için oluşturulmuştur. Ancak, gerekli işlevselliği sağlayan başka bir sürüm üzerinde çalıştırmak için çalışma zamanı'nın bir sürümü için derlenmiş bir .exe uygulama mümkündür.  
  
 Bunu gerçekleştirmek için çalışma zamanı sürüm bilgileri içeren bir app.config dosyası sağlamanız `supportedRuntime` etiketi.  
  
 Çalışma zamanında, app.config dosyası biçiminde bir adı olmalıdır *dosyaadı.uzn*.config, burada *dosyaadı.uzn* için uygulamanın yeniden başlatılması yürütülebilir dosya adıdır ve aynı dizinde olmalıdır yürütülebilir. Örneğin, uygulamanızın TestApp.exe olarak adlandırılmışsa, app.config dosyasını TestApp.exe.config olarak adlandırılır.  
  
 Birden fazla çalışma zamanı sürümü belirtirseniz ve uygulama çalıştıran birden fazla yüklenmiş çalışma zamanı sürümüne sahip bir bilgisayarda, uygulamanın yapılandırma dosyasında belirtilir ve yüklü ilk sürümünü kullanır.  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: .NET Framework sürümünü hedeflemek için bir uygulama yapılandırma](http://msdn.microsoft.com/en-us/5247b307-89ca-417b-8dd0-e8f9bd2f4717).  
  
 Sürüm 1.0 veya Visual C++ tarafından oluşturulmuş bir uygulama CLR sürüm 1.1 çalıştırmak için derleyici kullanarak derlenmelidir [/clr:initialAppDomain](../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Masaüstü uygulamaları dağıtma](../ide/deploying-native-desktop-applications-visual-cpp.md)