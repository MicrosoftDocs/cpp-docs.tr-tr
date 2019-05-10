---
title: MFC MBCS DLL Eklentisi
ms.date: 05/08/2019
helpviewer_keywords:
- MBCS
- MFC
ms.openlocfilehash: 20145b200a0f8bac8ccb461331d4d233a3b0251e
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/10/2019
ms.locfileid: "65524813"
---
# <a name="mfc-mbcs-dll-add-on"></a>MFC MBCS DLL Eklentisi

MFC desteği ve çok baytlı karakter kümesi (MBCS) kitaplıklarını, Visual Studio 2013 ve Visual Studio yüklemesi sırasında ek bir adım gerektirir.

**Visual Studio 2013'ün**: Varsayılan olarak, Visual Studio 2013'te yüklü MFC kitaplıkları yalnızca Unicode geliştirmeyi destekliyor. MBCS DLL'leri olan Visual Studio 2013'te bir MFC projesi oluşturmak için ihtiyacınız **karakter kümesi** özelliğini **kullanmak çok baytlı karakter kümesi** veya **ayarlı değil**. DLL indirme [Visual Studio 2013 Multibyte MFC Kitaplığı](https://www.microsoft.com/download/details.aspx?id=40770).

**Visual Studio 2015**: Unicode ve MBCS MFC DLL Visual C++ Kurulum bileşenleri dahil, ancak desteği MFC varsayılan olarak yüklü değil. Visual C++ ve Visual Studio kurulumunda isteğe bağlı yükleme yapılandırmalardır. MFC yüklü olduğundan emin olmak için seçin **özel** Kurulum ve altında **programlama dilleri**, emin **Visual C++** ve **Microsoft Foundation C++ sınıfları** seçilir. Zaten Visual Studio yüklü değilse, bir MFC projesi oluşturmaya çalışırken, Visual C++ ve/veya MFC yüklemeniz istenir.

**Visual Studio 2017 ve üzeri**: Unicode ve MBCS MFC DLL ile birlikte yüklenen **C++ ile masaüstü geliştirme** seçtiğinizde iş yükü **MFC ve ATL desteği** gelen **isteğe bağlı bileşenler** bölmesi. Yüklemenizin bu bileşenlerin içermiyorsa gidin **dosya | Yeni projeler** tıklayın ve iletişim **açık Visual Studio yükleyicisi** bağlantı.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Kitaplık Sürümleri](../mfc/mfc-library-versions.md)
