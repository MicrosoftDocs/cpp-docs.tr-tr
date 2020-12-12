---
description: 'Daha fazla bilgi edinin: TN070: MFC pencere sınıfı adları'
title: 'TN070: MFC Pencere Sınıfı Adları'
ms.date: 11/04/2016
helpviewer_keywords:
- window class names [MFC]
- TN070 [MFC]
ms.assetid: 90617912-dd58-4a7c-9082-ced71736d7cd
ms.openlocfilehash: 963f343f480a5805a3c1ec3cf5499583a17535ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214526"
---
# <a name="tn070-mfc-window-class-names"></a>TN070: MFC Pencere Sınıfı Adları

> [!NOTE]
> Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

MFC Windows, pencerenin özelliklerini yansıtan dinamik olarak oluşturulmuş bir sınıf adı kullanır. MFC, uygulama tarafından oluşturulan çerçeve pencereleri, görünümler ve açılan pencereler için dinamik olarak sınıf adları oluşturur. Bir MFC uygulaması tarafından oluşturulan iletişim kutuları ve denetimler, söz konusu pencerenin sınıfının Windows tarafından sağlanan adına sahiptir.

Kendi pencere sınıfınızı kaydederek ve bunu [ön](../mfc/reference/cwnd-class.md#precreatewindow)planda bir geçersiz kılmada kullanarak dinamik olarak sağlanmış sınıf adını değiştirebilirsiniz. MFC tarafından sağlanan sınıf adları aşağıdaki iki formdan birine uyum ister:

```
Afx:%x:%x
Afx:%x:%x:%x:%x:%x
```

Karakterlerin yerini alan onaltılık basamaklar `%x` [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) yapısındaki verilerden doldurulur. MFC bu tekniği, aynı **WNDCLASS** yapılarını gerektiren birden çok C++ sınıfının aynı kayıtlı pencere sınıfını paylaşabilmesini sağlamak için kullanır. Çoğu basit Win32 uygulamasının aksine, MFC uygulamalarında yalnızca bir **WndProc** vardır; bu sayede, zaman ve bellek tasarrufu sağlamak Için **WNDCLASS** yapılarını kolayca paylaşabilirsiniz. `%x`Yukarıda gösterilen karakterlerin değiştirilebilen değerleri şunlardır:

- **WNDCLASS. HINSTANCE**

- **WNDCLASS. Style**

- **WNDCLASS. hCursor**

- **WNDCLASS. hbrBackground**

- **WNDCLASS. HICON**

İlk form ( `Afx:%x:%x` ), **hCursor**, **hbrBackground** ve **HICON** 'ın tamamen **null** olduğu durumlarda kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)<br/>
[TN020: KIMLIK adlandırma ve numaralandırma kuralları](../mfc/tn020-id-naming-and-numbering-conventions.md)
