---
title: 'TN070: MFC pencere sınıfı adları'
ms.date: 11/04/2016
helpviewer_keywords:
- window class names [MFC]
- TN070 [MFC]
ms.assetid: 90617912-dd58-4a7c-9082-ced71736d7cd
ms.openlocfilehash: 1d9b5de07bcc2545df6294557d1ac9f9d29e856c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513347"
---
# <a name="tn070-mfc-window-class-names"></a>TN070: MFC pencere sınıfı adları

> [!NOTE]
>  Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

MFC Windows, pencerenin özelliklerini yansıtan dinamik olarak oluşturulmuş bir sınıf adı kullanır. MFC, uygulama tarafından oluşturulan çerçeve pencereleri, görünümler ve açılan pencereler için dinamik olarak sınıf adları oluşturur. Bir MFC uygulaması tarafından oluşturulan iletişim kutuları ve denetimler, söz konusu pencerenin sınıfının Windows tarafından sağlanan adına sahiptir.

Kendi pencere sınıfınızı kaydederek ve bunu [ön](../mfc/reference/cwnd-class.md#precreatewindow)planda bir geçersiz kılmada kullanarak dinamik olarak sağlanmış sınıf adını değiştirebilirsiniz. MFC tarafından sağlanan sınıf adları aşağıdaki iki formdan birine uyum ister:

```
Afx:%x:%x
Afx:%x:%x:%x:%x:%x
```

`%x` Karakterlerin yerini alan onaltılık basamaklar [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) yapısındaki verilerden doldurulur. MFC bu tekniği, aynı C++ **WNDCLASS** yapılarını gerektiren birden çok sınıfın aynı kayıtlı pencere sınıfını paylaşabilmesi için kullanır. Çoğu basit Win32 uygulamasının aksine, MFC uygulamalarında yalnızca bir **WndProc**vardır; bu sayede, zaman ve bellek tasarrufu sağlamak Için **WNDCLASS** yapılarını kolayca paylaşabilirsiniz. Yukarıda gösterilen `%x` karakterlerin değiştirilebilen değerleri şunlardır:

- **WNDCLASS. HINSTANCE**

- **WNDCLASS. Style**

- **WNDCLASS. hCursor**

- **WNDCLASS. hbrBackground**

- **WNDCLASS. HICON**

İlk`Afx:%x:%x`form (), **hCursor**, **hbrBackground**ve **HICON** 'ın tamamen **null**olduğu durumlarda kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)<br/>
[TN020: Kimlik Adlandırma ve Numaralandırma Kuralları](../mfc/tn020-id-naming-and-numbering-conventions.md)
