---
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
ms.openlocfilehash: 92db11778de7d31bbab67e649cd58e264da331e6
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58787770"
---
# <a name="understanding-the-dependencies-of-a-visual-c-application"></a>Visual C++ Uygulaması Bağımlılıklarını Anlama

Bir uygulamanın bağımlı hangi Visual C++ kitaplıklarının belirlemek için proje özelliklerini görüntüleyebilirsiniz. (Çözüm Gezgini'nde projeye sağ tıklayın ve seçin **özellikleri** açmak için **özellik sayfaları** iletişim kutusu.) Windows 8 ve daha önce bağımlılık bağımlılıkları daha kapsamlı bir resim sunan Denetçisi'ni (depends.exe) de kullanabilirsiniz. Windows daha yeni sürümleri için [lucasg/bağımlılıkları](https://github.com/lucasg/Dependencies) Aracı (garanti Microsoft tarafından değil bir üçüncü taraf araç budur.) benzer bir işlevsellik sağlar

İçinde **özellik sayfaları** iletişim kutusunun altındaki çeşitli sayfaları inceleyebilirsiniz **yapılandırma özellikleri** bağımlılıkları anlamak için. Örneğin, projeniz MFC kitaplıklarını kullanıyorsa ve seçtiğiniz **MFC kullanımı**, **MFC'yi bir ortak DLL'de** üzerinde **yapılandırma özellikleri**, **genel**  sayfasında, uygulamanızın çalışma zamanında bağımlı MFC DLL'lerine bağlı gibi mfc\<sürüm > .dll. Uygulamanız MFC kullanmıyorsa, seçerseniz, CRT kitaplığına bağlı olabilir bir **çalışma zamanı kitaplığı** değerini **hata ayıklama çok iş parçacıklı DLL (/ MDd)** veya **çok iş parçacıklı DLL (/ MD)** üzerinde **yapılandırma özellikleri**, **C/C++**, **kod oluşturma** sayfası.

Depends.exe öğesini kullanarak yükleme zamanında uygulamaya bağlı DLL'lerin listesini ve kendi Gecikmeli yüklenen DLL'lerin listesini inceleyebilirsiniz. Tam zamanında dinamik olarak yüklenen DLL'lerin listesini almak istiyorsanız, tüm kod yollarının uygulandığından emin oluncaya kadar uygulamayı test etmek için depends.exe dosyasında profil oluşturma özelliğini kullanabilirsiniz. Profil oluşturma oturumunu sonlandırdığınızda, depends.exe hangi DLL'lerin dinamik olarak çalışma zamanı sırasında yüklendiğini gösterir.

Depends.exe kullanırken, bir DLL'nin başka bir DLL'ye veya belirli bir DLL sürümüne bağımlılığı olabileceğini unutmayın. Depends.exe'yi geliştirme bilgisayarında veya hedef bir bilgisayarda kullanabilirsiniz. Geliştirme bilgisayarında, depends.exe, bir uygulamayı desteklemesi gereken DLL'leri bildirir. Hedef bilgisayarda bir uygulamanın çalışmasını sağlama konusunda sorun yaşıyorsanız, depends.exe dosyasını bu bilgisayara kopyalayıp uygulamayı araçta açabilir ve böylece gerekli DLL'lerin eksik ya da hatalı olup olmadığını belirleyebilirsiniz.

Uygulamanızın hangi DLL'lere bağlı olduğunu bildiğinizde, başka bir bilgisayara dağıtım yaparken uygulamanızla birlikte yeniden dağıtmanız gereken DLL'leri belirleyebilirsiniz. Çoğu durumda, sistem DLL'lerini yeniden dağıtmanız gerekmez, ancak Visual C++ kitaplıklarını DLL'leri dağıtmanız gerekebilir. Daha fazla bilgi için [belirleme hangi DLL'lerin yeniden dağıtılacağını](determining-which-dlls-to-redistribute.md).

## <a name="see-also"></a>Ayrıca bkz.

[Masaüstü uygulamalarını dağıtma](deploying-native-desktop-applications-visual-cpp.md)
