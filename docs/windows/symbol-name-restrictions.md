---
title: Sembol Adı Kısıtlamaları
ms.date: 11/04/2016
f1_keywords:
- vc.editors.symbol.restrictions.name
helpviewer_keywords:
- symbol names
- symbols [C++], names
- restrictions, symbol names
ms.assetid: 4ae7f695-ca86-4f4b-989a-fe6f89650ff7
ms.openlocfilehash: 7b6d8804dc7f3c9768dc9e86fde0e708f67c43fe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624872"
---
# <a name="symbol-name-restrictions"></a>Sembol Adı Kısıtlamaları

Sembol adı kısıtlamaları aşağıdaki gibidir:

- Tüm [sembolleri](../windows/symbols-resource-identifiers.md) uygulama kapsamında benzersiz olmalıdır. Bu, üstbilgi dosyalarında çakışan sembol tanımlarını engeller.

- Sembol adı için geçerli karakterler, A-Z, a-z, 0-9 ve alt çizgi (_) içerir.

- Sembol adları bir sayı ile başlayamaz ve 247 karakter ile sınırlıdır.

- Sembol adları boşluk içeremez.

- Sembol adları büyük/küçük harfe duyarlı değildir, ancak ilk sembol tanımı durumu korunur. Sembolleri tanımlar üstbilgi dosyası, kaynaklar bir kaynak dosyasında tanımlanan başvurmak için hem kaynak derleyici/Düzenleyicisi hem de C++ programlarının tarafından kullanılır. Yalnızca kaynak derleyici/Düzenleyici tek bir sembole başvuru olarak her iki adlarını görür ancak C++ program iki ayrı sembolleri görür durumunda, iki sembol adları için farklı.

   > [!NOTE]
   > Standart sembol adı düzeni izlemeyin varsa (ID*_[keyword]) özetlenen aşağıda ve kaynak kod dosyasını derlenmeye çalışılıyor, kaynak kod derleyici bilinen bir anahtar sözcük görünüşte rastgele hatayla sonuçlanır. aynı olacak şekilde, sembol adı olur. tanı koymak güç oluşturma. Bunu önlemek için standart adlandırma şeması izliyor.

Sembol adları, kaynak veya temsil ettikleri nesne türünü belirten açıklayıcı önekleri vardır. Açıklayıcı bu ön ekler metin birleşim kimliği ile başlayın Microsoft Foundation Class Kitaplığı'nı (MFC) aşağıdaki tabloda gösterilen simge adlandırma kurallarını kullanır.

|Kategori|Ön eki|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|--------------|------------|---------|
|Kaynaklar|IDR_ IDD_ IDC_ IDI_ IDB_|Hızlandırıcı veya menü (ve ilişkili ya da özel kaynaklar) imleç simgesi bit eşlem iletişim kutusu|
|Menü öğeleri|ID_|Menü öğesi|
|Komutlar|ID_|Komut|
|Denetimleri ve alt pencereler|IDC_|Denetim|
|Dizeler|IDS_|Dize tablosunda dize|
|MFC|AFX_|Önceden tanımlanmış MFC sembolleri için ayrılmış|

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Sembolü veya Sembol Adını (ID) Değiştirme](../windows/changing-a-symbol-or-symbol-name-id.md)<br/>
[Sembol Değeri Kısıtlamaları](../windows/symbol-value-restrictions.md)<br/>
[Önceden Tanımlanmış Sembol Kimlikleri](../windows/predefined-symbol-ids.md)