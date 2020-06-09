---
title: MFC MBCS DLL Eklentisi
ms.date: 12/02/2019
helpviewer_keywords:
- MBCS
- MFC
ms.openlocfilehash: 522bd5cf573aa3a0b24f14bc50f23b0d0e300d2e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625345"
---
# <a name="mfc-mbcs-dll-add-on"></a>MFC MBCS DLL Eklentisi

MFC ve çok baytlı karakter kümesi (MBCS) kitaplıkları için destek, Visual Studio 2013 ve sonraki sürümlerde Visual Studio yüklemesi sırasında ek bir adım gerektirir.

**Visual Studio 2013**: varsayılan olarak, VISUAL STUDIO 2013 yüklenen MFC kitaplıkları yalnızca Unicode geliştirmeyi destekler. Bir MFC projesi oluşturmak için, **karakter kümesi** özelliği **çok baytlık karakter kümesi kullan** veya **ayarlanmamış**olarak ayarlanmış bir Visual Studio 2013 içinde MFC projesi oluşturmanız gerekir. [Visual Studio 2013 Için çok BAYTLı MFC Kitaplığı](https://www.microsoft.com/download/details.aspx?id=40770)'nda dll 'yi indirin.

**Visual Studio 2015**: hem Unicode hem de MBCS mfc dll 'leri Visual C++ Kurulum bileşenlerine dahildir, ancak MFC desteği varsayılan olarak yüklenmez. Visual C++ ve MFC, Visual Studio kurulumunda isteğe bağlı yükleme yapılandırmalarına sahiptir. MFC 'nin yüklü olduğundan emin olmak için, kurulum 'da **özel** ' i seçin ve **programlama dilleri**' nin altında, **C++ için** **Visual C++** ve Microsoft Foundation sınıfları seçildiğinden emin olun. Visual Studio 'Yu önceden yüklediyseniz, bir MFC projesi oluşturmaya çalıştığınızda Visual C++ ve/veya MFC 'yi yüklemek isteyip istemediğiniz sorulur.

**Visual Studio 2017 ve üzeri**: Visual Studio yükleyicisi programındaki **isteğe bağlı bileşenler** bölmesinde **MFC ve atl desteği '** nı seçtiğinizde, Unicode ve MBCS MFC DLL 'leri C++ iş yüküyle **Masaüstü geliştirmeyle** birlikte yüklenir. Yüklemeniz bu bileşenleri içermiyorsa, **dosyaya gidin | Yeni projeler** iletişim kutusunda **Aç Visual Studio yükleyicisi** bağlantısına tıklayın. Daha fazla bilgi için bkz. [Visual Studio 'Yu yükler](/visualstudio/install/install-visual-studio).

## <a name="see-also"></a>Ayrıca bkz.

[MFC kitaplık sürümleri](mfc-library-versions.md)
