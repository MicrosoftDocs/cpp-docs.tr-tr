---
title: MFC MBCS DLL Eklentisi
ms.date: 1/04/2018
helpviewer_keywords:
- MBCS
- MFC
ms.openlocfilehash: a78425ac92aa9ddfe7f0b1b61dde915b3e088383
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558925"
---
# <a name="mfc-mbcs-dll-add-on"></a>MFC MBCS DLL Eklentisi

MFC desteği ve çok baytlı karakter kümesi (MBCS) kitaplıklarını Visual Studio 2013, 2015 ve 2017 Visual Studio yüklemesi sırasında ek bir adım gerektirir.

**Visual Studio 2013'ün**: varsayılan olarak, Visual Studio 2013'te yüklü MFC kitaplıkları yalnızca Unicode geliştirmeyi destekliyor. MBCS DLL'leri olan Visual Studio 2013'te bir MFC projesi oluşturmak için ihtiyacınız **karakter kümesi** özelliğini **kullanmak çok baytlı karakter kümesi** veya **ayarlı değil**. DLL indirme [Visual Studio 2013 Multibyte MFC Kitaplığı](https://www.microsoft.com/download/details.aspx?id=40770).

**Visual Studio 2015**: hem Unicode ve MBCS MFC DLL Visual C++ Kurulum bileşenleri dahil edilir, ancak desteği MFC varsayılan olarak yüklü değil. Visual C++ ve Visual Studio kurulumunda isteğe bağlı yükleme yapılandırmalardır. MFC yüklü olduğundan emin olmak için seçin **özel** Kurulum ve altında **programlama dilleri**, emin **Visual C++** ve **Microsoft Foundation C++ sınıfları** seçilir. Zaten Visual Studio yüklü değilse, bir MFC projesi oluşturmaya çalışırken, Visual C++ ve/veya MFC yüklemeniz istenir.

**Visual Studio 2017**: Unicode ve MBCS MFC DLL'leri birlikte yüklenen **C++ ile masaüstü geliştirme** seçtiğinizde iş yükü **MFC ve ATL desteği** gelen **isteğe bağlı Bileşenleri** bölmesi. Yüklemenizin bu bileşenlerin içermiyorsa gidin **dosya | Yeni projeler** tıklayın ve iletişim **açık Visual Studio yükleyicisi** bağlantı.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Kitaplık Sürümleri](../mfc/mfc-library-versions.md)

