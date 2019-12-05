---
title: MFC MBCS DLL Eklentisi
ms.date: 12/02/2019
helpviewer_keywords:
- MBCS
- MFC
ms.openlocfilehash: fe74e0639664b6a6a86a4c3269f174de441002f4
ms.sourcegitcommit: 8762a3f9b5476b4dee03f0ee8064ea606550986e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/04/2019
ms.locfileid: "74810361"
---
# <a name="mfc-mbcs-dll-add-on"></a>MFC MBCS DLL Eklentisi

MFC ve çok baytlı karakter kümesi (MBCS) kitaplıkları için destek, Visual Studio 2013 ve sonraki sürümlerde Visual Studio yüklemesi sırasında ek bir adım gerektirir.

**Visual Studio 2013**: varsayılan olarak, VISUAL STUDIO 2013 yüklenen MFC kitaplıkları yalnızca Unicode geliştirmeyi destekler. Bir MFC projesi oluşturmak için, **karakter kümesi** özelliği **çok baytlık karakter kümesi kullan** veya **ayarlanmamış**olarak ayarlanmış bir Visual Studio 2013 içinde MFC projesi oluşturmanız gerekir. [Visual Studio 2013 Için çok BAYTLı MFC Kitaplığı](https://www.microsoft.com/download/details.aspx?id=40770)'nda dll 'yi indirin.

**Visual Studio 2015**: hem Unicode hem de MBCS MFC DLL 'leri görsel C++ kurulum BILEŞENLERINE dahildir, ancak MFC desteği varsayılan olarak yüklenmez. Visual C++ ve MFC, Visual Studio kurulumunda isteğe bağlı yükleme yapılandırmalarına sahiptir. MFC 'nin yüklü olduğundan emin olmak için, kurulum 'da **özel** ' i seçin ve **programlama dilleri**' nin altında, **görsel C++**  ve **Microsoft Foundation sınıfları C++**  seçeneğinin seçildiğinden emin olun. Visual Studio 'Yu önceden yüklediyseniz, bir MFC projesi oluşturmaya çalıştığınızda görsel C++ ve/veya MFC 'yi yüklemek isteyip istemediğiniz sorulur.

**Visual Studio 2017 ve üzeri**: Visual Studio yükleyicisi programındaki **isteğe bağlı bileşenler** bölmesinde **MFC ve atl desteği '** ni seçtiğinizde, Unicode ve MBCS MFC DLL 'leri iş yüküyle **Masaüstü geliştirmeyle C++**  birlikte yüklenir. Yüklemeniz bu bileşenleri içermiyorsa, **dosyaya gidin | Yeni projeler** iletişim kutusunda **Aç Visual Studio yükleyicisi** bağlantısına tıklayın. Daha fazla bilgi için bkz. [Visual Studio 'Yu yükler](/visualstudio/install/install-visual-studio).

## <a name="see-also"></a>Ayrıca bkz.

[MFC Kitaplık Sürümleri](../mfc/mfc-library-versions.md)
