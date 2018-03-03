---
title: MFC MBCS DLL eklentisi | Microsoft Docs
ms.custom: 
ms.date: 1/04/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MBCS
- MFC
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d6f134110ff95956cc37d6e038a680ff27cbc298
ms.sourcegitcommit: 56f6fce7d80e4f61d45752f4c8512e4ef0453e58
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/12/2018
---
# <a name="mfc-mbcs-dll-add-on"></a>MFC MBCS DLL Eklentisi

MFC desteği ve çok baytlı karakter kümesi (MBCS) başlatılamadığından, 2015 ve 2017 Visual Studio 2013'te Visual Studio yüklemesi sırasında ek bir adım gerektirir.

**Visual Studio 2013**: varsayılan olarak, Visual Studio 2013'te yüklü MFC kitaplıkları yalnızca Unicode geliştirme desteği. MBCS dll bir MFC projesine sahip Visual Studio 2013'te oluşturmak için gereksinim duyduğunuz **karakter kümesi** özelliğini **kullanımı çok baytlı karakter kümesi** veya **ayarlanmamış**. DLL karşıdan [Visual Studio 2013 için birden çok baytlı MFC Kitaplığı](https://www.microsoft.com/en-us/download/details.aspx?id=40770).

**Visual Studio 2015**: hem Unicode ve MBCS MFC DLL'leri Visual C++ Kurulum bileşenleri dahil, ancak MFC varsayılan olarak yüklü olmayan dil desteği. Visual C++ ve MFC Visual Studio kurulumunda isteğe bağlı yükleme bağlantılardır. MFC yüklendiğinden emin olmak için tercih **özel** kurulumunda ve altında **programlama dilleri**, olduğundan emin olun **Visual C++** ve **Microsoft Foundation C++ sınıfları** seçilir. Visual Studio'nun zaten yüklediyseniz, bir MFC projesine oluşturma girişiminde bulunduğunuzda Visual C++ ve/veya MFC yüklemeniz istenir.

**Visual Studio 2017**: Unicode ve MBCS MFC DLL'leri birlikte yüklenen **C++ ile masaüstü geliştirme** seçtiğinizde iş yükü **MFC ve ATL desteği** gelen  **İsteğe bağlı bileşenler** bölmesi. Yüklemenizi bu bileşenlerin içermiyorsa, Yükleyiciden başlatabilirsiniz **yeni projeler** kullanarak iletişim **açık Visual Studio yükleyicisi** bağlantı.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Kitaplık Sürümleri](../mfc/mfc-library-versions.md)

