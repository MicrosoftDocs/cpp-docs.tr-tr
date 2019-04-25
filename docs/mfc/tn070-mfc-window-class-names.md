---
title: 'TN070: MFC pencere sınıfı adları'
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.classes
helpviewer_keywords:
- window class names [MFC]
- TN070 [MFC]
ms.assetid: 90617912-dd58-4a7c-9082-ced71736d7cd
ms.openlocfilehash: 8b06f7b3656284de18632185877fdbe382343f95
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62168043"
---
# <a name="tn070-mfc-window-class-names"></a>TN070: MFC pencere sınıfı adları

> [!NOTE]
>  Aşağıdaki Teknik Not çevrimiçi belgelere ilk eklenmiştir beri güncelleştirilmemiş. Eski veya yanlış sonuç olarak, bazı yordamlar ve konular olabilir. En son bilgiler için bu konuyu çevrimiçi belge dizininde arama önerilir.

MFC windows penceresi özelliklerini yansıtan bir dinamik olarak oluşturulan sınıf adı kullanın. MFC sınıf adları çerçeve pencereleri, görünümler ve uygulama tarafından üretilen açılır pencereleri için dinamik olarak oluşturur. İletişim kutuları ve bir MFC uygulaması tarafından üretilen denetimleri penceresinin söz konusu sınıf için Windows tarafından sağlanan ad var.

Kendi pencere sınıfı kaydediliyor ve içinde geçersiz kılma kullanılarak dinamik olarak sağlanan sınıf adını değiştir [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow). MFC tarafından sağlanan sınıf adlarını iki aşağıdaki biçimlerden birini uygun:

```
Afx:%x:%x
Afx:%x:%x:%x:%x:%x
```

Yerini onaltılık basamak `%x` karakter doldurulur verilerden gelen [WNDCLASS](/windows/desktop/api/winuser/ns-winuser-tagwndclassa) yapısı. MFC bu tekniği kullanır böylece birden fazla C++ sınıfları aynı gerektiren **WNDCLASS** yapıları aynı kayıtlı pencere sınıfı paylaşabilir. En basit Win32 uygulamalardan farklı olarak, yalnızca bir MFC uygulamaları sahip **WNDPROC**, bu nedenle, bir kolayca paylaşabilirsiniz **WNDCLASS** süresi ve bellek kaydetmek için yapılar. Değiştirilebilir değerlerini `%x` yukarıda gösterilen karakter aşağıdaki gibidir:

- **WNDCLASS.hInstance**

- **WNDCLASS.style**

- **WNDCLASS.hCursor**

- **WNDCLASS.hbrBackground**

- **WNDCLASS.hIcon**

İlk form (`Afx:%x:%x`) kullanıldığında **hCursor**, **hbrBackground**, ve **hIcon** tümü **NULL**.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)<br/>
[TN020: Kimlik adlandırma ve numaralandırma kuralları](../mfc/tn020-id-naming-and-numbering-conventions.md)
