---
title: Pencere Nesneleri
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], window
- Windows window [MFC]
- MFC, windows
- frame windows [MFC], C++ window objects
- window objects [MFC]
- windows [MFC], C++ window objects
- window messages [MFC]
- HWND
- messages [MFC], Windows
- Visual C++, window objects [MFC]
- HWND, window objects [MFC]
ms.assetid: 28b33ce2-af05-4617-9d03-1cb9a02be687
ms.openlocfilehash: 3e20ef1f3643b9e802c7cdc399d3436ceadeae79
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566705"
---
# <a name="window-objects"></a>Pencere Nesneleri

MFC sağlar sınıfını [CWnd](../mfc/reference/cwnd-class.md) yalıtılacak `HWND` pencere tanıtıcısı. `CWnd` Nesnedir, farklı bir C++ pencere nesnesi, `HWND` temsil eden bir Windows penceresi ancak içeren. Kullanma `CWnd` kendi alt penceresi türetmek için sınıflar veya birçok MFC sınıflarını birini türetilen `CWnd`. Sınıf `CWnd` çerçeve pencereleri, iletişim kutuları, alt pencereler, denetimler ve denetim çubukları araç çubukları gibi dahil olmak üzere tüm pencereler için temel sınıftır. İyi bir anlayış [bir C++ pencere nesnesi ile bir HWND arasındaki ilişkiyi](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md) MFC ile etkili programlama için önemlidir.

MFC, bazı varsayılan işlevselliği ve windows yönetimi sağlar, ancak kendi sınıftan türetilip `CWnd` ve onun üye işlevleri sağlanan işlevselliği özelleştirmek için kullanın. Windows alt oluşturarak oluşturabilirsiniz bir `CWnd` nesne ve arama kendi [Oluştur](../mfc/reference/cwnd-class.md#create) üye işlev ve alt öğe pencerelerini kullanarak özelleştirme `CWnd` üye işlevleri. Öğesinden türetilen nesneler katıştırabilirsiniz [CView](../mfc/reference/cview-class.md)form görünümleri ya da bir çerçeve penceresindeki ağaç görünümleri gibi. Birden çok belgelerinizi sınıfı tarafından sağlanan Bölümlendirici bölmeleri üzerinden görünümlerini destekleyebilir [CSplitterWnd](../mfc/reference/csplitterwnd-class.md).

Her nesne sınıfından türetilmiş `CWnd` üzerinden Windows ileti eşlemesi veya komut kimlikleri için kendi işleyicilerinizi bir ileti eşlemesi içerir.

Windows için nasıl kullanılacağını öğrenmek için iyi bir kaynaktır programlama hakkında genel belgeleri `CWnd` kapsülleyen üye işlevleri, `HWND` API'leri.

## <a name="functions-for-operating-on-a-cwnd"></a>Bir CWnd üzerinde çalışmak işlevleri

`CWnd` ve kendi [türetilen pencere sınıfları](../mfc/derived-window-classes.md) oluşturucular ve Yıkıcılar nesnesini başlatmak için üye işlevleri Windows yapılar oluşturmak ve kapsüllenmiş erişim sağlayan `HWND`. `CWnd` Ayrıca, pencerenin durumu, güncelleştirme, koordinatları, dönüştürme erişme iletileri göndermek için Windows API'ları kapsülleyen işlevleri sağlar kaydırma, Pano ve diğer birçok görevi erişme. Alan çoğu Windows pencere yönetimi API'leri bir `HWND` bağımsız değişken üye işlevleri kapsüllenmiş `CWnd`. İşlevleri ve bunların parametrelerini adlarını saklanır `CWnd` üye işlevi. Windows tarafından Kapsüllenen API'ler ile ilgili bilgiler için `CWnd`, sınıfına bakın [CWnd](../mfc/reference/cwnd-class.md).

## <a name="cwnd-and-windows-messages"></a>CWnd ve Windows iletileri

Birincil amaçlarından biri `CWnd` WM_PAINT ya da WM_MOUSEMOVE gibi Windows iletileri işlemek için bir arabirim sağlar. Üye işlevlerinin çoğu `CWnd` standart iletileri için işleyiciler — bu tanımlayıcısıyla başlayarak **afx_msg** ve ön ek "," gibi `OnPaint` ve `OnMouseMove`. [İleti işleme ve eşleme](../mfc/message-handling-and-mapping.md) iletileri ve ileti işleme ayrıntılı olarak ele alınır. Bilgi vardır, framework'ün windows hem de özel amaçlar için kendiniz oluşturmanız için eşit oranda geçerlidir.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Bir C++ pencere nesnesi ile bir HWND arasındaki ilişki](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md)

- [Türetilen pencere sınıfları](../mfc/derived-window-classes.md)

- [Pencereler oluşturma](../mfc/creating-windows.md)

- [Pencere nesnelerini yok etme](../mfc/destroying-window-objects.md)

- [Bir CWnd'i HWND'inden Ayırma](../mfc/detaching-a-cwnd-from-its-hwnd.md)

- [Pencere nesneleriyle çalışma](../mfc/working-with-window-objects.md)

- [Cihaz bağlamları](../mfc/device-contexts.md): Windows cihaz çizim bağımsız nesneleri

- [Grafik nesneler](../mfc/graphic-objects.md): kalemler, Fırçalar, yazı tipleri, bit eşlemler, paletler, bölgeler

## <a name="see-also"></a>Ayrıca Bkz.

[Windows](../mfc/windows.md)

