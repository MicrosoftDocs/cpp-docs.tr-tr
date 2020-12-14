---
description: 'Daha fazla bilgi edinin: önceki çalışma zamanı sürümünde C++/CLR uygulaması çalıştırma'
title: Önceki Çalışma Zamanı Sürümünde C++ /clr Uygulaması Çalıştırma
ms.date: 11/04/2016
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
ms.openlocfilehash: 3b1bbc2906e4b347bb954c799cb9e412202a17ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247221"
---
# <a name="running-a-c-clr-application-on-a-previous-runtime-version"></a>Önceki Çalışma Zamanı Sürümünde C++ /clr Uygulaması Çalıştırma

Aksi belirtilmediği takdirde, bir C++ .NET Framework uygulaması derleyicinin uygulamayı derlemek için kullandığı ortak dil çalışma zamanı (CLR) sürümünde çalışacak şekilde oluşturulmuştur. Ancak, bir çalışma zamanının bir sürümü için oluşturulan bir. exe uygulaması, gerekli işlevselliği sağlayan başka herhangi bir sürümde çalıştırmak mümkündür.

Bunu gerçekleştirmek için, etiketinde çalışma zamanı sürüm bilgilerini içeren bir app.config dosyası sağlayın `supportedRuntime` .

Çalışma zamanında, app.config dosyası *filename. ext*. config biçiminde bir ada sahip olmalıdır; burada *filename. ext* , uygulamayı başlatan yürütülebilir dosyanın adıdır ve yürütülebilir dosya ile aynı dizinde olmalıdır. Örneğin, uygulamanız TestApp.exe olarak adlandırılmışsa app.config dosya TestApp.exe.config olarak adlandırılır.

Birden fazla çalışma zamanı sürümü belirtirseniz ve uygulama birden fazla yüklü çalışma zamanı sürümü olan bir bilgisayarda çalışıyorsa, uygulama yapılandırma dosyasında belirtilen ilk sürümü kullanır ve yüklenir.

## <a name="see-also"></a>Ayrıca bkz.

[Masaüstü uygulamaları dağıtma](deploying-native-desktop-applications-visual-cpp.md)
