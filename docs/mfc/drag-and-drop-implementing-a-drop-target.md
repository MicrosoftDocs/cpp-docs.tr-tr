---
title: 'Sürükle ve bırak: bir bırakma hedefi uygulama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE drag and drop [MFC], implementing drop targets
- OLE drag and drop [MFC], drop target
- drag and drop [MFC], drop target
ms.assetid: 0689f1ec-5326-4008-b226-4b373c881358
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fae6a5ef0e25b0e81b21dce9069c599e59e1c431
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377773"
---
# <a name="drag-and-drop-implementing-a-drop-target"></a>Sürükle ve Bırak: Bir Bırakma Hedefi Uygulama

Bu makalede bir bırakma hedefi uygulama yapma özetlenmektedir. Bir bırakma hedefi uygulama bir bırakma kaynağı uygulama değerinden biraz daha fazla iş alır, ancak yine de oldukça basit bir işlemdir. Bu teknikler OLE olmayan uygulamaları için de geçerlidir.

#### <a name="to-implement-a-drop-target"></a>Bir bırakma hedefi uygulama

1. Her bir görünümde bir bırakma hedefi olmasını istediğiniz uygulama için bir üye değişkeni ekleyin. Bu üye değişkeni türünde olmalıdır `COleDropTarget` veya ondan türetilmiş bir sınıf.

1. İşler görünümü sınıfınızın işlevden **WM_CREATE** iletisi (genellikle `OnCreate`), yeni üye değişkenin çağrı `Register` üye işlevi. `Revoke` otomatik olarak görünümünüzü kaldırıldığında sizin için çağrılır.

1. Aşağıdaki işlevleri geçersiz kılar. Uygulamanızın genelinde aynı davranışı istiyorsanız, bu işlevler görünümü sınıfınızda geçersiz kılar. Yalıtılmış durumlarda davranışını değiştirmek ya da olmayan bırakarak etkinleştirmek istediğiniz istiyorsanız`CView` windows, bu işlevleri geçersiz kılma, `COleDropTarget`-türetilmiş sınıf.

    |Geçersiz kıl|İzin vermek için|
    |--------------|--------------|
    |`OnDragEnter`|İşlemleri penceresinde gerçekleşecek şekilde bırakın. İmleç ilk kez pencereye girdiğinde çağırılır.|
    |`OnDragLeave`|Sürükleme işlemi belirtilen pencere ayrıldığında özel davranış.|
    |`OnDragOver`|İşlemleri penceresinde gerçekleşecek şekilde bırakın. İmleç pencerenin arasında sürüklendiğinde çağırılır.|
    |`OnDrop`|Belirtilen pencereye bırakılan veri işleme.|
    |`OnScrollBy`|Kaydırma hedef penceresinde gerekli olduğunda özel davranış.|

MAINVIEW bakın. CPP dosyasına başka bir deyişle MFC OLE örnekle [OCLIENT](../visual-cpp-samples.md) bu işlevler birlikte nasıl çalıştığını bir örneği.

Daha fazla bilgi için bkz.:

- [Bir bırakma kaynağı uygulama](../mfc/drag-and-drop-implementing-a-drop-source.md)

- [Oluşturma ve OLE veri nesneleri ve veri kaynakları yok etme](../mfc/data-objects-and-data-sources-creation-and-destruction.md)

- [OLE veri nesneleri ve veri kaynakları düzenleme](../mfc/data-objects-and-data-sources-manipulation.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Sürükleme ve Bırakma (OLE)](../mfc/drag-and-drop-ole.md)<br/>
[COleDropTarget Sınıfı](../mfc/reference/coledroptarget-class.md)
