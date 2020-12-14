---
description: 'Hakkında daha fazla bilgi edinin: TN003: nesnelere Windows tanıtıcıları eşleme'
title: 'TN003: Pencere İşleyicilerini Nesnelere Eşleme'
ms.date: 11/04/2016
f1_keywords:
- vc.mapping
helpviewer_keywords:
- TN003
- handle maps
- Windows handles to objects [MFC]
- mappings [MFC], Windows handles to objects
ms.assetid: fbea9f38-992c-4091-8dbc-f29e288617d6
ms.openlocfilehash: e4a0bfa2315ec2b9d67d884d4fdebe314599f454
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216047"
---
# <a name="tn003-mapping-of-windows-handles-to-objects"></a>TN003: Pencere İşleyicilerini Nesnelere Eşleme

Bu notta, Windows nesne tanıtıcılarını C++ nesnelerine eşlemeyi destekleyen MFC yordamları açıklanmaktadır.

## <a name="the-problem"></a>Sorun

Windows nesneleri genellikle çeşitli [tanıtıcı](/windows/win32/WinProg/windows-data-types) nesneleri tarafından temsıl edilir MFC sınıfları C++ nesneleriyle Windows nesne tutamaçlarını sarın. MFC sınıf kitaplığının tanıtıcı kaydırma işlevleri, belirli bir tanıtıcıya sahip olan Windows nesnesini sarmaladığı C++ nesnesini bulmanızı sağlar. Ancak, bazen bir nesne bir C++ sarmalayıcı nesnesine sahip değildir ve bu saatlerde sistem, C++ sarmalayıcı işlevi görecek geçici bir nesne oluşturur.

Tanıtıcı haritaları kullanan Windows nesneleri aşağıdaki gibidir:

- HWND ([CWnd](../mfc/reference/cwnd-class.md) ve `CWnd` -türetilen sınıflar)

- HDC ([CDC](../mfc/reference/cdc-class.md) ve `CDC` -türetilen sınıflar)

- HMENU ([CMenu](../mfc/reference/cmenu-class.md))

- HPEN ([CGdiObject](../mfc/reference/cgdiobject-class.md))

- HBRUSH ( `CGdiObject` )

- HFONT ( `CGdiObject` )

- HBIT eşlem ( `CGdiObject` )

- HPALETTE ( `CGdiObject` )

- HRGN ( `CGdiObject` )

- HıMAGELIST ([CImageList](../mfc/reference/cimagelist-class.md))

- YUVA ([CSocket](../mfc/reference/csocket-class.md))

Bu nesnelerden herhangi birine yönelik bir tanıtıcı verildiğinde, statik yöntemi çağırarak tutamacı sarmalayan MFC nesnesini bulabilirsiniz `FromHandle` . Örneğin, *HWND* ADLı bir HWND verildiğinde, aşağıdaki satır HWND 'yi sarmalayan öğesine bir işaretçi döndürür `CWnd` : 

```
CWnd::FromHandle(hWnd)
```

*HWND* 'nin belirli bir sarmalayıcı nesnesi yoksa, `CWnd` *HWND* sarmalamak için geçici bir oluşturma oluşturulur. Bu, herhangi bir tanıtıcıdan geçerli bir C++ nesnesi elde etme olanağı sunar.

Sarmalayıcı nesneniz olduktan sonra, öğesini sarmalayıcı sınıfının ortak üye değişkeninden elde edebilirsiniz. Bir `CWnd` , *m_hWnd* söz konusu nesnenin HWND 'sini içerir.

## <a name="attaching-handles-to-mfc-objects"></a>MFC nesnelerine Işleyiciler iliştirme

Yeni oluşturulan bir tanıtıcı sarmalayıcı nesnesi ve bir Windows nesnesine yönelik bir tanıtıcı verildiğinde, `Attach` işlevi bu örnekte olduğu gibi çağırarak iki ilişki de ilişkilendirebilirsiniz:

```
CWnd myWnd;
myWnd.Attach(hWnd);
```

Bu, *myWnd* ve *HWND* ile ilişkili kalıcı haritada bir giriş yapar. Çağırmak `CWnd::FromHandle(hWnd)` Şimdi *myWnd* için bir işaretçi döndürüyor. *MyWnd* silindiğinde, yıkıcı otomatik olarak Windows [destroyıwindow](/windows/win32/api/winuser/nf-winuser-destroywindow) işlevini çağırarak *HWND* 'yi yok eder. Bu istenmiyorsa, *myWnd* 'in yok edileceği (normalde, *myWnd* 'in tanımlandığı kapsamdan ayrılırken), *HWND* *myWnd* 'den ayrılmalıdır. `Detach`Yöntemi bunu yapar.

```
myWnd.Detach();
```

## <a name="more-about-temporary-objects"></a>Geçici nesneler hakkında daha fazla bilgi

Geçici nesneler `FromHandle` , zaten sarmalayıcı nesnesine sahip olmayan bir tanıtıcı verildiğinde oluşturulur. Bu geçici nesneler tanıtıcılarından ayrılır ve işlevler tarafından silinir `DeleteTempMap` . Varsayılan olarak [CWinThread:: OnIdle](../mfc/reference/cwinthread-class.md#onidle) `DeleteTempMap` , geçici tanıtıcı eşlemelerini destekleyen her sınıf için otomatik olarak çağırır. Yani, geçici bir nesne işaretçisinin, işaretçinin alındığı işlevden çıkış noktasından geçmiş olduğunu varsaymayacak anlamına gelir.

## <a name="wrapper-objects-and-multiple-threads"></a>Sarmalayıcı nesneler ve birden çok Iş parçacığı

Hem geçici hem de kalıcı nesneler iş parçacığı başına temelinde tutulur. Diğer bir deyişle, bir iş parçacığı geçici veya kalıcı olmasına bakılmaksızın başka bir iş parçacığının C++ sarmalayıcı nesnelerine erişemez.

Bu nesneleri bir iş parçacığından diğerine geçirmek için, her zaman yerel türleri olarak gönderin `HANDLE` . C++ sarmalayıcı nesnesini bir iş parçacığından diğerine geçirmek genellikle beklenmeyen sonuçlara neden olur.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
