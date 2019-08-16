---
title: 'TN003: Windows tanıtıcılarının nesneleriyle eşleme'
ms.date: 11/04/2016
f1_keywords:
- vc.mapping
helpviewer_keywords:
- TN003
- handle maps
- Windows handles to objects [MFC]
- mappings [MFC], Windows handles to objects
ms.assetid: fbea9f38-992c-4091-8dbc-f29e288617d6
ms.openlocfilehash: 45492963e1b686e03eb59c320fdc3d52d1534f7d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513529"
---
# <a name="tn003-mapping-of-windows-handles-to-objects"></a>TN003: Windows tanıtıcılarının nesneleriyle eşleme

Bu notta, Windows nesne tanıtıcılarını C++ nesnelere EŞLEMEYI destekleyen MFC yordamları açıklanmaktadır.

## <a name="the-problem"></a>Sorun

Windows nesneleri genellikle çeşitli [tanıtıcı](/windows/win32/WinProg/windows-data-types) nesneleri tarafından temsıl edilir MFC sınıflarının nesneleri ile C++ Windows nesne tutamaçlarını sarması. MFC sınıf kitaplığının tanıtıcı kaydırma işlevleri, belirli bir tanıtıcıya sahip olan Windows C++ nesnesini sarmaladığı nesneyi bulmanızı sağlar. Ancak, bazen bir nesne C++ sarmalayıcı nesnesine sahip değildir ve bu saatlerde sistem C++ sarmalayıcı olarak davranacak geçici bir nesne oluşturur.

Tanıtıcı haritaları kullanan Windows nesneleri aşağıdaki gibidir:

- HWND ([CWnd](../mfc/reference/cwnd-class.md) ve `CWnd`-türetilen sınıflar)

- HDC ([CDC](../mfc/reference/cdc-class.md) ve `CDC`-türetilen sınıflar)

- HMENU ([CMenu](../mfc/reference/cmenu-class.md))

- HPEN ([CGdiObject](../mfc/reference/cgdiobject-class.md))

- HBRUSH (`CGdiObject`)

- HFONT (`CGdiObject`)

- HBIT EŞLEM`CGdiObject`()

- HPALETTE (`CGdiObject`)

- HRGN (`CGdiObject`)

- HıMAGELIST ([CImageList](../mfc/reference/cimagelist-class.md))

- YUVA ([CSocket](../mfc/reference/csocket-class.md))

Bu nesnelerden herhangi birine yönelik bir tanıtıcı verildiğinde, statik yöntemi `FromHandle`çağırarak TUTAMACı sarmalayan MFC nesnesini bulabilirsiniz. Örneğin, *HWND*adlı bir HWND verildiğinde, aşağıdaki satır `CWnd` *HWND*'yi sarmalayan öğesine bir işaretçi döndürür:

```
CWnd::FromHandle(hWnd)
```

*HWND* 'nin belirli bir sarmalayıcı nesnesi yoksa, *HWND*sarmalamak için `CWnd` geçici bir oluşturma oluşturulur. Bu, herhangi bir tanıtıcıdan geçerli C++ bir nesne elde etmek mümkün hale getirir.

Sarmalayıcı nesneniz olduktan sonra, öğesini sarmalayıcı sınıfının ortak üye değişkeninden elde edebilirsiniz. Bu durumda `CWnd`, *m_hWnd* bu nesne için hwnd içerir.

## <a name="attaching-handles-to-mfc-objects"></a>MFC nesnelerine Işleyiciler iliştirme

Yeni oluşturulan bir tanıtıcı sarmalayıcı nesnesi ve bir Windows nesnesine yönelik bir tanıtıcı verildiğinde, `Attach` işlevi bu örnekte olduğu gibi çağırarak iki ilişki de ilişkilendirebilirsiniz:

```
CWnd myWnd;
myWnd.Attach(hWnd);
```

Bu, *myWnd* ve *HWND*ile ilişkili kalıcı haritada bir giriş yapar. Çağırmak `CWnd::FromHandle(hWnd)` şimdi *myWnd*için bir işaretçi döndürüyor. *MyWnd* silindiğinde, yıkıcı otomatik olarak Windows [destroyıwindow](/windows/win32/api/winuser/nf-winuser-destroywindow) işlevini çağırarak *HWND* 'yi yok eder. Bu istenmiyorsa, *myWnd* 'in yok edileceği (normalde, myWnd 'in tanımlandığı kapsamdan ayrılırken), *HWND* *myWnd* 'den ayrılmalıdır. `Detach` Yöntemi bunu yapar.

```
myWnd.Detach();
```

## <a name="more-about-temporary-objects"></a>Geçici nesneler hakkında daha fazla bilgi

Geçici nesneler `FromHandle` , zaten sarmalayıcı nesnesine sahip olmayan bir tanıtıcı verildiğinde oluşturulur. Bu geçici nesneler tanıtıcılarından ayrılır ve `DeleteTempMap` işlevler tarafından silinir. Varsayılan olarak [CWinThread:: OnIdle](../mfc/reference/cwinthread-class.md#onidle) , `DeleteTempMap` geçici tanıtıcı eşlemelerini destekleyen her sınıf için otomatik olarak çağırır. Yani, geçici bir nesne işaretçisinin, işaretçinin alındığı işlevden çıkış noktasından geçmiş olduğunu varsaymayacak anlamına gelir.

## <a name="wrapper-objects-and-multiple-threads"></a>Sarmalayıcı nesneler ve birden çok Iş parçacığı

Hem geçici hem de kalıcı nesneler iş parçacığı başına temelinde tutulur. Diğer bir deyişle, bir iş parçacığı geçici veya kalıcı C++ olmasına bakılmaksızın başka bir iş parçacığının sarmalayıcı nesnelerine erişemez.

Bu nesneleri bir iş parçacığından diğerine geçirmek için, her zaman yerel `HANDLE` türleri olarak gönderin. C++ Sarmalayıcı nesnesini bir iş parçacığından diğerine geçirmek genellikle beklenmeyen sonuçlara neden olur.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
