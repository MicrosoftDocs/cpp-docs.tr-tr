---
title: MFC MBCS DLL Eklentisi
ms.date: 1/04/2018
helpviewer_keywords:
- MBCS
- MFC
ms.openlocfilehash: 2fdbb5dd862c7d1a8845813c6234fea9e902c1f9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62238536"
---
# <a name="mfc-mbcs-dll-add-on"></a>MFC MBCS DLL Eklentisi

MFC desteği ve çok baytlı karakter kümesi (MBCS) kitaplıklarını Visual Studio 2013, 2015 ve 2017 Visual Studio yüklemesi sırasında ek bir adım gerektirir.

**Visual Studio 2013'ün**: Varsayılan olarak, Visual Studio 2013'te yüklü MFC kitaplıkları yalnızca Unicode geliştirmeyi destekliyor. MBCS DLL'leri olan Visual Studio 2013'te bir MFC projesi oluşturmak için ihtiyacınız **karakter kümesi** özelliğini **kullanmak çok baytlı karakter kümesi** veya **ayarlı değil**. DLL indirme [Visual Studio 2013 Multibyte MFC Kitaplığı](https://www.microsoft.com/download/details.aspx?id=40770).

**Visual Studio 2015**: Unicode ve MBCS MFC DLL Visual C++ Kurulum bileşenleri dahil, ancak desteği MFC varsayılan olarak yüklü değil. Visual C++ ve Visual Studio kurulumunda isteğe bağlı yükleme yapılandırmalardır. MFC yüklü olduğundan emin olmak için seçin **özel** Kurulum ve altında **programlama dilleri**, emin **Visual C++** ve **Microsoft Foundation C++ sınıfları** seçilir. Zaten Visual Studio yüklü değilse, bir MFC projesi oluşturmaya çalışırken, Visual C++ ve/veya MFC yüklemeniz istenir.

**Visual Studio 2017**: Unicode ve MBCS MFC DLL ile birlikte yüklenen **C++ ile masaüstü geliştirme** seçtiğinizde iş yükü **MFC ve ATL desteği** gelen **isteğe bağlı bileşenler** bölmesi. Yüklemenizin bu bileşenlerin içermiyorsa gidin **dosya | Yeni projeler** tıklayın ve iletişim **açık Visual Studio yükleyicisi** bağlantı.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Kitaplık Sürümleri](../mfc/mfc-library-versions.md)
