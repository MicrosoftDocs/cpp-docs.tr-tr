---
description: 'Hakkında daha fazla bilgi edinin: Visual C++ uygulamasının bağımlılıklarını anlama'
title: Visual C++ Uygulaması Bağımlılıklarını Anlama
ms.date: 11/04/2016
helpviewer_keywords:
- application deployment [C++], dependencies
- Dependency Walker
- dependencies [C++], application deployment and
- deploying applications [C++], dependencies
- DUMPBIN utility
- DLLs [C++], dependencies
- depends.exe
- libraries [C++], application deployment issues
ms.assetid: 62a44c95-c389-4c5f-82fd-07d7ef09dbf9
ms.openlocfilehash: ff18d594edf6d35541655075de6f6e951ea42b88
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336567"
---
# <a name="understanding-the-dependencies-of-a-visual-c-application"></a>Visual C++ Uygulaması Bağımlılıklarını Anlama

Bir uygulamanın hangi Visual C++ kitaplıklarına bağlı olduğunu anlamak için, proje özelliklerini görüntüleyebilirsiniz. (Çözüm Gezgini, projeye sağ tıklayın ve **Özellikler** ' i seçerek **Özellik sayfaları** iletişim kutusunu açın.) Windows 8 ve önceki sürümlerde, bağımlılıkların daha kapsamlı bir resmini sağlayan bağımlılık denetçisi 'ni (depends.exe) de kullanabilirsiniz. Windows 'un daha yeni sürümleri için [lucasg/Dependencies](https://github.com/lucasg/Dependencies) aracı benzer işlevler sağlar (Bu, Microsoft tarafından garanti edilmediği üçüncü taraf bir araçtır.)

**Özellik sayfaları** iletişim kutusunda, bağımlılıkları anlamak Için **yapılandırma özellikleri** altında çeşitli sayfaları inceleyebilirsiniz. Örneğin, projeniz MFC kitaplıklarını kullanıyorsa ve **MFC kullan**' ı seçerseniz, **yapılandırma özellikleri**, **genel** sayfasındaki **bir paylaşılan DLL 'de MFC 'yi kullanarak** , çalışma zamanında uygulamanız MFC. dll gibi MFC DLL 'lerine göre değişir \<version> . Uygulamanız MFC kullanmıyorsa, **yapılandırma özellikleri**, **C/C++**, **kod üretimi** sayfasında, **çok iş parçacıklı hata ayıklama dll (/MDD)** veya **çok iş parçacıklı DLL (/MD)** **çalışma zamanı kitaplığı** değeri seçerseniz bu, CRT kitaplığına bağlı olabilir.

depends.exe kullanarak, yükleme zamanında uygulamayla bağlantılı dll 'lerin listesini ve Gecikmeli yüklenen dll 'lerin bir listesini inceleyebilirsiniz. Çalışma zamanında dinamik olarak yüklenen dll 'lerin tümüyle bir listesini almak istiyorsanız, tüm kod yollarının uygulanmış olduğundan emin olana kadar uygulamayı test etmek için depends.exe profil oluşturma özelliğini kullanabilirsiniz. Profil oluşturma oturumunu sona erdirmek depends.exe, çalışma zamanında dinamik olarak yüklenen dll 'Leri gösterir.

Depends.exe kullanırken, bir DLL'nin başka bir DLL'ye veya belirli bir DLL sürümüne bağımlılığı olabileceğini unutmayın. Depends.exe'yi geliştirme bilgisayarında veya hedef bir bilgisayarda kullanabilirsiniz. Geliştirme bilgisayarında, depends.exe, bir uygulamayı desteklemesi gereken DLL'leri bildirir. Hedef bilgisayarda bir uygulamanın çalışmasını sağlama konusunda sorun yaşıyorsanız, depends.exe dosyasını bu bilgisayara kopyalayıp uygulamayı araçta açabilir ve böylece gerekli DLL'lerin eksik ya da hatalı olup olmadığını belirleyebilirsiniz.

Uygulamanızın hangi DLL'lere bağlı olduğunu bildiğinizde, başka bir bilgisayara dağıtım yaparken uygulamanızla birlikte yeniden dağıtmanız gereken DLL'leri belirleyebilirsiniz. Çoğu durumda, sistem dll 'Lerini yeniden dağıtmanız gerekmez, ancak dll 'Leri Visual C++ kitaplıkları için yeniden dağıtmanız gerekebilir. Daha fazla bilgi için bkz. [hangi dll 'lerin yeniden dağıtılacağını belirleme](determining-which-dlls-to-redistribute.md).

## <a name="see-also"></a>Ayrıca bkz.

[Masaüstü uygulamaları dağıtma](deploying-native-desktop-applications-visual-cpp.md)
