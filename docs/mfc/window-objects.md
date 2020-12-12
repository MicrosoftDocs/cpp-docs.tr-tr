---
description: 'Daha fazla bilgi edinin: pencere nesneleri'
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
ms.openlocfilehash: 5a7755dfecc8205279785a6452b04c3f8dc429d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214500"
---
# <a name="window-objects"></a>Pencere Nesneleri

MFC bir pencere tanıtıcısını kapsüllemek için [CWnd](../mfc/reference/cwnd-class.md) sınıfını sağlar `HWND` . `CWnd`Nesnesi, `HWND` bir Windows penceresini temsil eden, ancak Içeren bir C++ pencere nesnesidir. `CWnd`Kendi alt pencere sınıflarınızı türetmede kullanın veya öğesinden türetilmiş bırçok MFC sınıfından birini kullanın `CWnd` . Sınıf, `CWnd` çerçeve pencereleri, iletişim kutuları, alt pencereler, denetimler ve araç çubukları gibi denetim çubukları dahil tüm pencereler için temel sınıftır. [C++ pencere nesnesi Ile HWND arasındaki ilişkiyi](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md) iyi anlamak, MFC ile etkili programlama için çok önemlidir.

MFC, Windows 'un bazı varsayılan işlevlerini ve yönetimini sağlar, ancak sağlanan işlevselliği özelleştirmek için kendi sınıfınızı ' den türetebilir `CWnd` ve üye işlevlerini kullanabilirsiniz. Bir nesne oluşturup üye `CWnd` [Oluştur](../mfc/reference/cwnd-class.md#create) işlevini çağırarak alt pencereler oluşturabilir, ardından üye işlevlerini kullanarak alt pencereleri özelleştirebilirsiniz `CWnd` . Bir çerçeve penceresinde form görünümleri veya ağaç görünümleri gibi [CView](../mfc/reference/cview-class.md)'dan türetilmiş nesneleri katıştırabilirsiniz. Aynı şekilde, [CSplitterWnd](../mfc/reference/csplitterwnd-class.md)sınıfı tarafından sağlanan Bölümlendirici bölmeleri aracılığıyla belgelerinizin birden çok görünümünü destekleyebilirsiniz.

Sınıfından türetilmiş her nesne `CWnd` , Windows iletilerini veya komut kimliklerini kendi işleyicilerinizden eşleyebileceğiniz bir ileti haritası içerir.

Windows için programlama hakkında genel belgeler `CWnd` , API 'leri kapsülleyen üye işlevlerinin nasıl kullanılacağını öğrenmek için iyi bir kaynaktır `HWND` .

## <a name="functions-for-operating-on-a-cwnd"></a>CWnd üzerinde çalışma işlevleri

`CWnd` ve [türetilmiş pencere sınıfları](../mfc/derived-window-classes.md) , nesneyi başlatmak, temeldeki Windows yapılarını oluşturmak ve kapsüllene erişmek için oluşturucular, Yıkıcılar ve üye işlevlerini sağlar `HWND` . `CWnd` Ayrıca, ileti göndermek için Windows API 'Lerini kapsülleyen, pencere durumuna erişen, koordinatları dönüştüren, pano 'Ya erişen ve diğer birçok görev gibi üye işlevleri de sağlar. Bağımsız değişken alan çoğu Windows penceresi-yönetim API 'Leri `HWND` üye işlevleri olarak kapsüllenir `CWnd` . İşlevlerin ve parametrelerinin adları, `CWnd` üye işlevinde korunur. Tarafından kapsüllenmiş Windows API 'Leri hakkında daha fazla bilgi için `CWnd` bkz. Class [CWnd](../mfc/reference/cwnd-class.md).

## <a name="cwnd-and-windows-messages"></a>CWnd ve Windows Iletileri

' Nin birincil amaçlarından biri, `CWnd` WM_PAINT veya WM_MOUSEMOVE gibi Windows iletilerini işlemek için bir arabirim sağlamaktır. Öğesinin üye işlevlerinin birçoğu `CWnd` Standart iletiler için işleyicileridir (tanımlayıcı **afx_msg** başlayarak ve ve gibi "on" öneki) `OnPaint` `OnMouseMove` . [Ileti işleme ve eşleme](../mfc/message-handling-and-mapping.md) iletileri ve ileti işlemeyi ayrıntılı olarak içerir. Bu bilgiler, Framework pencerelerinin eşit olarak uygulandığı ve özel amaçlar için sizin oluşturduğunuz olanlardır.

### <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [C++ pencere nesnesi ve HWND arasındaki ilişki](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md)

- [Türetilen pencere sınıfları](../mfc/derived-window-classes.md)

- [Pencereler oluşturma](../mfc/creating-windows.md)

- [Pencere nesnelerini yok etme](../mfc/destroying-window-objects.md)

- [Bir CWnd 'i HWND 'den ayırma](../mfc/detaching-a-cwnd-from-its-hwnd.md)

- [Pencere nesneleriyle çalışma](../mfc/working-with-window-objects.md)

- [Cihaz bağlamları](../mfc/device-contexts.md): Windows çizim cihazını bağımsız hale getirme nesneleri

- [Grafik nesneleri](../mfc/graphic-objects.md): kalemler, fırçalar, fontlar, bit eşlemler, paletler, bölgeler

## <a name="see-also"></a>Ayrıca bkz.

[Windows](../mfc/windows.md)
