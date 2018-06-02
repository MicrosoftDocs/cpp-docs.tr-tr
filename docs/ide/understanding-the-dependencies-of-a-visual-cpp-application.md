---
title: Visual C++ uygulaması bağımlılıklarını anlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da2aadeba69a8be29627650ba6ef24516098a8e3
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "33338789"
---
# <a name="understanding-the-dependencies-of-a-visual-c-application"></a>Visual C++ Uygulaması Bağımlılıklarını Anlama
Bir uygulamanın bağımlı hangi Visual C++ kitaplıkları belirlemek için proje özelliklerini görüntüleyebilirsiniz. (Çözüm Gezgini'nde projeye sağ tıklayın ve seçin **özellikleri** açmak için **özellik sayfaları** iletişim kutusu.) Bağımlılıklara dair daha kapsamlı bir resim sunan Bağımlılık Denetçisi'ni (depends.exe) de kullanabilirsiniz.  
  
 İçinde **özellik sayfaları** iletişim kutusu, altındaki çeşitli sayfalar incelemek **yapılandırma özellikleri** bağımlılıkları anlamak için. Örneğin, MFC kitaplıklarını projenize kullanır ve seçerseniz **kullanın, MFC**, **MFC'yi paylaşılan DLL'de** üzerinde **yapılandırma özellikleri**, **genel**  sayfasında, uygulamanızın çalışma zamanında bağlıdır MFC DLL'leri gibi mfc\<sürüm > .dll. Uygulamanızı MFC kullanmıyorsa, seçerseniz, CRT kitaplığına bağımlı olabilir bir **çalışma zamanı kitaplığı** değerini **çok iş parçacıklı hata ayıklama DLL (/ MDd)** veya **çok iş parçacıklı DLL (/ MD)** üzerinde **yapılandırma özellikleri**, **C/C++**, **kod oluşturma** sayfası.  
  
 Uygulamanızın bağımlı hangi DLL'lerin belirlemek için daha kapsamlı bir şekilde uygulamayı açmak için bağımlılık bekçisi (depends.exe) kullanmaktır. Aracından indirebilirsiniz [bağımlılık bekçisi](http://go.microsoft.com/fwlink/p/?LinkId=132640) web sitesi.  
  
 Depends.exe kullanarak, yükleme zamanında uygulamanın bağlantılı DLL'ler listesini ve onun Gecikmeli yüklenen DLL'ler listesini inceleyebilirsiniz. Çalışma zamanında dinamik olarak yüklenen DLL tam bir listesini almak istiyorsanız, tüm kod yollarının uygulandığından emin kadar uygulamayı test etmek için depends.exe dosyasında profil oluşturma özelliğini kullanabilirsiniz. Profil oluşturma oturumu sonlandırdığınızda, depends.exe hangi DLL'lerin çalışma zamanında dinamik olarak yüklendiğini gösterir.  
  
 Depends.exe kullanırken, bir DLL'nin başka bir DLL'ye veya belirli bir DLL sürümüne bağımlılığı olabileceğini unutmayın. Depends.exe'yi geliştirme bilgisayarında veya hedef bir bilgisayarda kullanabilirsiniz. Geliştirme bilgisayarında, depends.exe, bir uygulamayı desteklemesi gereken DLL'leri bildirir. Hedef bilgisayarda bir uygulamanın çalışmasını sağlama konusunda sorun yaşıyorsanız, depends.exe dosyasını bu bilgisayara kopyalayıp uygulamayı araçta açabilir ve böylece gerekli DLL'lerin eksik ya da hatalı olup olmadığını belirleyebilirsiniz.  
  
 Uygulamanızın hangi DLL'lere bağlı olduğunu bildiğinizde, başka bir bilgisayara dağıtım yaparken uygulamanızla birlikte yeniden dağıtmanız gereken DLL'leri belirleyebilirsiniz. Çoğu durumda, sistem DLL'leri yeniden dağıtmanıza gerek yoktur, ancak Visual C++ kitaplıkları için DLL'leri dağıtmanız gerekebilir. Daha fazla bilgi için bkz: [belirleme hangi DLL'lerin yeniden dağıtılacağını](../ide/determining-which-dlls-to-redistribute.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Masaüstü uygulamaları dağıtma](../ide/deploying-native-desktop-applications-visual-cpp.md)