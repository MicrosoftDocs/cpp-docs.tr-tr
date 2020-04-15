---
title: 'TN070: MFC Pencere Sınıfı Adları'
ms.date: 11/04/2016
helpviewer_keywords:
- window class names [MFC]
- TN070 [MFC]
ms.assetid: 90617912-dd58-4a7c-9082-ced71736d7cd
ms.openlocfilehash: ad43f5af5d2e90cb5fc2bc90f0909c2b495b4a4c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373494"
---
# <a name="tn070-mfc-window-class-names"></a>TN070: MFC Pencere Sınıfı Adları

> [!NOTE]
> Aşağıdaki teknik not, çevrimiçi belgelere ilk olarak eklenmediğinden beri güncelleştirilemedi. Sonuç olarak, bazı yordamlar ve konular güncel veya yanlış olabilir. En son bilgiler için, çevrimiçi belge dizini ilgi alanı için arama nız önerilir.

MFC pencereleri, pencerenin özelliklerini yansıtan dinamik olarak oluşturulmuş bir sınıf adı kullanır. MFC, uygulama tarafından üretilen çerçeve pencereleri, görünümler ve açılır pencereler için sınıf adlarını dinamik olarak oluşturur. Bir MFC uygulaması tarafından üretilen iletişim kutuları ve denetimleri, söz konusu pencere sınıfı için Windows tarafından sağlanan ada sahiptir.

Dinamik olarak sağlanan sınıf adını kendi pencere sınıfınızı kaydederek ve [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow)geçersiz kılında kullanarak değiştirebilirsiniz. MFC tarafından sağlanan sınıf adları aşağıdaki iki formdan birine uyar:

```
Afx:%x:%x
Afx:%x:%x:%x:%x:%x
```

`%x` Karakterlerin yerini alan hex basamakları [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) yapısındaki verilerden doldurulur. MFC, aynı **WNDCLASS** yapıları gerektiren birden çok C++ sınıfının aynı kayıtlı pencere sınıfını paylaşabilmesi için bu tekniği kullanır. En basit Win32 uygulamalarının aksine, MFC uygulamaları sadece bir **WNDPROC'a**sahiptir, böylece zamandan ve bellekten tasarruf etmek için **WNDCLASS** yapılarını kolayca paylaşabilirsiniz. Yukarıda gösterilen `%x` karakterler için değiştirilebilir değerler aşağıdaki gibidir:

- **WNDCLASS.hInstance**

- **WNDCLASS.style**

- **WNDCLASS.hCursor**

- **WNDCLASS.hbrArka Plan**

- **WNDCLASS.hIcon**

İlk form`Afx:%x:%x`( ) **hCursor**, **hbrBackground**ve **hIcon** tüm **NULL**olduğunda kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)<br/>
[TN020: Kimlik Adlandırma ve Numaralandırma Kuralları](../mfc/tn020-id-naming-and-numbering-conventions.md)
