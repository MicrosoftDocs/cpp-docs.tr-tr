---
title: Windows Vista Ortak Denetimleri için Derleme Gereksinimleri
ms.date: 11/04/2016
helpviewer_keywords:
- common controls (MFC), build requirements
- common controls (MFC)
ms.assetid: 025f7d55-55a2-4dcd-8f62-02424e3dcc04
ms.openlocfilehash: 1a2e79d91a41ea178eeb6f74ec7fa7b22588b277
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57276903"
---
# <a name="build-requirements-for-windows-vista-common-controls"></a>Windows Vista Ortak Denetimleri için Derleme Gereksinimleri

Microsoft Foundation Class (MFC) kitaplığı, Windows ortak denetimleri sürüm 6.1 destekler. Windows Vista ortak denetimleri dahildir ve Kitaplığı Visual Studio SDK içinde dahil edilir. Kitaplığı, mevcut sınıfları ve yeni sınıflar geliştiren yeni ve Windows Vista ortak denetimleri destekleyen yöntemleri sağlar. Uygulamanızı oluştururken, aşağıdaki bölümlerde açıklanan derleme ve Geçiş gereksinimleri karşılamalıdır.

## <a name="compilation-requirements"></a>Derleme gereksinimleri

### <a name="supported-versions"></a>Desteklenen sürümler

Bazı yeni sınıflar ve yöntemler yalnızca Windows Vista desteği ve daha sonra while diğer yöntemleri, önceki işletim sistemlerini de destekler. Bir Not `Requirements` her yöntemi konudaki zaman gereken en düşük işletim sistemi Windows Vista belirtir.

Bilgisayarınızı Windows Vista çalışmıyor olsa bile bilgisayarınızda sürüm 6.1 MFC üstbilgi dosyalarındaki varsa, Windows Vista üzerinde çalışacak bir MFC uygulaması oluşturabilirsiniz. Ancak, Windows Vista için özellikle tasarlanmış ortak denetimleri, yalnızca bu sistemde çalışan ve önceki işletim sistemleri tarafından göz ardı edilir.

### <a name="supported-character-sets"></a>Desteklenen karakter kümeleri

Yeni Windows ortak denetimleri, yalnızca Unicode karakter kümesi ve ANSI karakter kümesini destekler. Uygulamanızı komut satırında, aşağıdaki tanımla her ikisi de kullanın (/ D) derleyici seçenekleri Unicode temel olarak belirtmek için karakter kümesi:

```
/D_UNICODE /DUNICODE
```

Visual Studio tümleşik geliştirme ortamında (IDE) uygulamanızı belirtebilmeniz **Unicode karakter kümesi** seçeneği **karakter kümesi** özelliğinde **genel**  Proje Özellikleri'nin düğümü.

Çeşitli MFC yöntemler ANSI sürümü kullanımdan kaldırıldı Windows ortak denetimleri sürüm 6.1 başlatılıyor. Daha fazla bilgi için [kullanım dışı ANSI API'ları](../mfc/deprecated-ansi-apis.md).

## <a name="migration-requirements"></a>Geçiş gereksinimleri

Windows ortak denetimleri sürüm 6.1 kullanan yeni bir MFC uygulaması oluşturmak için Visual Studio IDE kullanırsanız, IDE uygun bir bildirimi otomatik olarak bildirir. Ancak, Visual Studio'nun önceki bir sürümden varolan bir MFC uygulamasına geçirme ve yeni ortak denetimleri kullanmak istediğiniz, IDE otomatik olarak uygulamanızı yükseltmek için bildirim bilgileri sağlamaz. Bunun yerine, el ile aşağıdaki kaynak kodunda eklemeniz gerekir, **stdafx.h** dosyası:

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
