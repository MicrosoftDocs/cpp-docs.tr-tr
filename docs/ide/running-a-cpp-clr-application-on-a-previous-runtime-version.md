---
title: Önceki çalışma zamanı sürümünde C++ / clr uygulaması çalıştırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6510f7f3bd9a88f4b938d2646bad6750fe310def
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43688753"
---
# <a name="running-a-c-clr-application-on-a-previous-runtime-version"></a>Önceki Çalışma Zamanı Sürümünde C++ /clr Uygulaması Çalıştırma
Aksi belirtilmediği sürece, C++, .NET Framework uygulamasını uygulamayı oluşturmak için derleyicinin kullandığı ortak dil çalışma zamanı (CLR) sürüm üzerinde çalıştırmak için oluşturulmuştur. Ancak, bir sürüm gerekli işlevselliği sağlayan başka bir sürüm üzerinde çalıştırmak için çalışma zamanı için oluşturulmuş bir .exe uygulama mümkündür.  
  
 Bunu yapmak için çalışma zamanı sürüm bilgileri içeren bir app.config dosyası sağlayın. `supportedRuntime` etiketi.  
  
 Çalışma zamanında, app.config dosyası biçiminde bir ada sahip olmalıdır *dosyaadı.uzn*.config, burada *dosyaadı.uzn* uygulamanın yürütülebilir dosya adıdır ve aynı dizinde olmalıdır yürütülebilir. Örneğin, uygulamanızın TestApp.exe adlandırılmışsa, app.config dosyasına TestApp.exe.config olarak adlandırılır.  
  
 Birden fazla çalışma zamanı sürümü belirtin ve birden fazla yüklü çalışma zamanı sürümü olan bir bilgisayarda uygulama çalışır, uygulama yapılandırma dosyasında belirtilen ve yüklü ilk sürümü kullanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Masaüstü uygulamalarını dağıtma](../ide/deploying-native-desktop-applications-visual-cpp.md)