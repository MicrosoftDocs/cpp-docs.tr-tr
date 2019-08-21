---
title: Windows ortak denetimleri için derleme gereksinimleri
ms.date: 08/19/2019
helpviewer_keywords:
- Common Controls (MFC), build requirements
- Common Controls (MFC)
ms.assetid: 025f7d55-55a2-4dcd-8f62-02424e3dcc04
ms.openlocfilehash: 9ea90f95ba8e704cba5b22c5e7338659f0c5f033
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630854"
---
# <a name="build-requirements-for-windows-common-controls"></a>Windows ortak denetimleri için derleme gereksinimleri

Microsoft Foundation Class (MFC) kitaplığı [Windows ortak denetimlerini](/windows/win32/controls/common-controls-intro)destekler. Ortak denetimler Windows 'a dahil edilmiştir ve kitaplık Visual Studio 'Ya dahildir. MFC kitaplığı, var olan sınıfları ve Windows ortak denetimlerini destekleyen ek sınıfları ve yöntemleri geliştiren yeni yöntemler sağlar. Uygulamanızı yapılandırdığınızda, aşağıdaki bölümlerde açıklanan derleme ve geçiş gereksinimlerini izlemelisiniz.

## <a name="compilation-requirements"></a>Derleme gereksinimleri

### <a name="supported-versions"></a>Desteklenen sürümler

MFC ortak denetimlerin tüm sürümlerini destekler. Windows ortak denetimler sürümleri hakkında daha fazla bilgi için bkz. [ortak denetim sürümleri](/windows/win32/controls/common-control-versions).

### <a name="supported-character-sets"></a>Desteklenen karakter kümeleri

Windows ortak denetimleri, ANSI karakter kümesini değil yalnızca Unicode karakter kümesini destekler. Uygulamanızı komut satırında oluşturursanız, temel alınan karakter kümesi olarak Unicode belirtmek için aşağıdaki define (/D) derleyici seçeneklerini kullanın:

```
/D_UNICODE /DUNICODE
```

Uygulamanızı Visual Studio tümleşik geliştirme ortamında (IDE) oluşturursanız, proje özelliklerinin **genel** düğümündeki **karakter kümesi** özelliğinin **Unicode karakter kümesi** seçeneğini belirleyin.

## <a name="migration-requirements"></a>Geçiş gereksinimleri

Windows ortak denetimleri kullanan yeni bir MFC uygulaması oluşturmak için Visual Studio IDE 'yi kullanırsanız, IDE otomatik olarak uygun bir bildirim bildirir. Ancak, mevcut bir MFC uygulamasını Visual Studio 2005 veya önceki bir sürümden geçirirseniz ve ortak denetimleri kullanmak istiyorsanız, IDE uygulamanızı yükseltmek için bildirim bilgilerini otomatik olarak sağlamaz. Bunun yerine, aşağıdaki kaynak kodu önceden derlenmiş üstbilgi dosyanıza el ile eklemeniz gerekir:

```
#ifdef UNICODE
#if defined _M_IX86
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='x86' publicKeyToken='6595b64144ccf1df' language='*'\"")
#elif defined _M_IA64
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='ia64' publicKeyToken='6595b64144ccf1df' language='*'\"")
#elif defined _M_X64
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='amd64' publicKeyToken='6595b64144ccf1df' language='*'\"")
#else
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='*' publicKeyToken='6595b64144ccf1df' language='*'\"")
#endif
#endif
```

## <a name="see-also"></a>Ayrıca bkz.

[Genel MFC Konuları](../mfc/general-mfc-topics.md)<br/>
[Hiyerarşi Grafiği](../mfc/hierarchy-chart.md)<br/>
[Kullanım Dışı ANSI API'leri](../mfc/deprecated-ansi-apis.md)
