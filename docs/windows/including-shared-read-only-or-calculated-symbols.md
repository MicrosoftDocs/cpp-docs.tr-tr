---
title: Paylaşılan (salt okunur) veya hesaplanan sembolleri ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.shared.calculated
dev_langs:
- C++
helpviewer_keywords:
- symbols [C++], read-only
- symbols [C++], shared
- symbols [C++], calculated
- read-only symbols
- symbol directives
- calculated symbols
- shared symbols
ms.assetid: 32b77faf-a066-4371-a072-9a5b84c0766d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 329f1d21489b57130531db20014e249588f101a6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400516"
---
# <a name="including-shared-read-only-or-calculated-symbols"></a>Paylaşılan (Salt Okunur) veya Hesaplanan Sembolleri Ekleme

Geliştirme ortamını başka bir uygulama tarafından oluşturulan bir kaynak dosyasını okur ilk kez tüm bulunan üst bilgi dosyaları salt okunur olarak işaretler. Daha sonra kullanabileceğiniz [kaynak içerikleri iletişim kutusu](../windows/resource-includes-dialog-box.md) ek salt okunur sembol üst bilgi dosyaları eklemek için.

Çeşitli projeler arasında paylaşmak sembol dosyaları salt okunur sembol tanımlarını kullanmak isteyebilirsiniz nedenlerinden biri içindir.

Sembol değeri tanımlamak için basit bir tamsayı yerine ifadeler kullanan sembol tanımlarını ile mevcut kaynaklar varsa, dahil edilen sembol dosyalarını da kullanabilirsiniz. Örneğin:

```cpp
#define   IDC_CONTROL1 2100
#define   IDC_CONTROL2 (IDC_CONTROL1+1)  
```

Ortamı doğru olduğu sürece bu hesaplanan semboller yorumlar:

- Hesaplanan semboller salt okunur semboller dosyasındaki yerleştirilir.

- Kaynak dosyanız bu hesaplanan semboller zaten atanmış kaynaklar içeriyor.

- Bir sayısal ifade bekleniyor.

> [!NOTE]
> Bir dize veya sayısal bir ifadenin bekleniyorsa, ifade değerlendirilmez.

### <a name="to-include-shared-read-only-symbols-in-your-resource-file"></a>Paylaşılan (salt okunur) semboller kaynak dosyanıza eklemek için

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), .rc dosyasını sağ tıklatın ve seçin [kaynak içerikleri](../windows/resource-includes-dialog-box.md) kısayol menüsünden.

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

2. İçinde **salt okunur sembol yönergeleri** kutusunda, kullanmak `#include` salt okunur semboller tutmak istediğiniz dosyayı belirtmek için derleyici yönergesi.

   Dosya çağırmayın `Resource.h`, normalde ana sembol başlık dosyası tarafından kullanılan dosya adı olduğundan.

   > [!NOTE]
   > **Önemli** tam olarak yazdığınız sırada, salt okunur sembol yönergeleri kutusuna yazdığınız kaynak dosyasına dahil edilir. Ne tür emin yazım veya söz dizimi hataları içermiyor.

   Kullanım **salt okunur sembol yönergeleri** sembol tanımlarını yalnızca dosyalarla kutusuna. Kaynak tanımları eklemeyin; Aksi takdirde, yinelenen kaynak tanımları dosyası kaydedildiğinde oluşturulur.

3. Simgeler, belirtilen dosyada yerleştirin.

   Bu şekilde dahil dosyalarındaki semboller kaynak dosyanızı açın her zaman değerlendirilir, ancak dosyanızı her kaydettiğinizde, diskte değiştirilmez.

4. **Tamam**'ı tıklatın.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Sembol Adı Kısıtlamaları](../windows/symbol-name-restrictions.md)<br/>
[Sembol Değeri Kısıtlamaları](../windows/symbol-value-restrictions.md)<br/>
[Önceden Tanımlanmış Sembol Kimlikleri](../windows/predefined-symbol-ids.md)<br/>
[Semboller: Kaynak Tanımlayıcıları](../windows/symbols-resource-identifiers.md)