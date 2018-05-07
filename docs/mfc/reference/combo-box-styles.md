---
title: Birleşik giriş kutusu stilleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CBS_LOWERCASE
- CBS_SORT
- CBS_OWNERDRAWVARIABLE
- CBS_OEMCONVERT
- CBS_AUTOHSCROLL
- CBS_NOINTEGRALHEIGHT
- CBS_SIMPLE
- CBS_DROPDOWNLIST
- CBS_DROPDOWN
- CBS_UPPERCASE
- CBS_HASSTRINGS
- CBS_DISABLENOSCROLL
- CBS_OWNERDRAWFIXED
dev_langs:
- C++
helpviewer_keywords:
- CBS_OWNERDRAWVARIABLE constant [MFC]
- CBS_NOINTEGRALHEIGHT constant [MFC]
- CBS_SIMPLE constant [MFC]
- CBS_AUTOHSCROLL constant [MFC]
- CBS_OEMCONVERT constant [MFC]
- CBS_DISABLENOSCROLL constant [MFC]
- CBS_HASSTRINGS constant [MFC]
- CBS_LOWERCASE constant [MFC]
- CBS_SORT constant [MFC]
- CBS_DROPDOWN constant [MFC]
- CBS_OWNERDRAWFIXED constant [MFC]
- combo boxes [MFC], styles
- CBS_UPPERCASE constant [MFC]
- CBS_DROPDOWNLIST constant
ms.assetid: d21a5023-e6a2-495b-a6bd-010a515cbc63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9ec15f483d9a613e77ad07b6f7f306e84099bced
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="combo-box-styles"></a>Birleşik Giriş Kutusu Stilleri
Aşağıdaki birleşik giriş kutusu stilleri MFC'de kullanılabilir.  
  
-   **CBS_AUTOHSCROLL** kullanıcı satırın sonuna bir karakter yazdığında metni sağa düzenleme denetimindeki otomatik olarak kayar. Bu stili ayarlanmadı dikdörtgen sınırı içinde uygun metin izin verilir.  
  
-   **Cbs_dısablenoscroll** zaman liste kutusunda kaydırma için yeterli öğeleri içermiyor çubuğu devre dışı bırakılmış bir dikey kaydırma liste kutusu gösterir. Liste kutusu yeterli öğeleri içermediğinde, bu stili kaydırma çubuğu gizlenir.  
  
-   **CBS_DROPDOWN** benzer **cbs_sımple**dışında kullanıcı düzenleme denetimi yanındaki simge seçmedikçe liste kutusunu görüntülenmez.  
  
-   **Cbs_dropdownlıst** benzer **CBS_DROPDOWN**dışında düzenleme denetimi liste kutusunda geçerli seçim görüntüleyen bir statik metin öğe ile değiştirilir.  
  
-   **Cbs_hasstrıngs** sahip çizim birleşik giriş kutusu dizeleri oluşan öğeleri içerir. Uygulamayı kullanabilmeniz için bellek ve dizeleri işaretçileri birleşik giriş kutusu tutar `GetText` belirli bir öğenin metni almak için üye işlevi.  
  
-   **CBS_LOWERCASE** seçimi alanını ve listenin tüm metni küçük harfe dönüştürür.  
  
-   **Cbs_noıntegralheıght** birleşik giriş kutusu boyutunu tam olarak birleşik giriş kutusu oluşturduğunuzda uygulama tarafından belirtilen boyut olduğunu belirtir. Normalde, böylece birleşik giriş kutusu kısmi öğeleri görüntülemez Windows birleşik giriş kutusu boyutları.  
  
-   **CBS_OEMCONVERT** birleşik giriş kutusu düzenleme denetimine girilen metin ANSI karakter kümesinden OEM karakter kümesi ve ANSI sonra geri dönüştürülür. Uygulama çağırdığında bu uygun karakter dönüştürme sağlar `AnsiToOem` birleşik giriş kutusu ANSI dizesinde OEM karakterlerine dönüştürmek için Windows işlevi. Bu stili ile oluşturulan birleşik giriş kutuları için geçerlidir ve dosya adlarını içeren birleşik giriş kutuları için en kullanışlıdır **cbs_sımple** veya **CBS_DROPDOWN** stilleri.  
  
-   **Cbs_ownerdrawfıxed** liste kutusu sahibi içeriğini çizmek için sorumlu; liste kutusunda öğeleri aynı yüksekliği olur.  
  
-   **Cbs_ownerdrawvarıable** liste kutusu sahibi içeriğini çizmek için sorumlu; liste kutusunda öğeleri yükseklik değişkeninde olur.  
  
-   **Cbs_sımple** liste kutusunu her zaman görüntülenir. Seçilen liste kutusunda düzenleme denetimine görüntülenir.  
  
-   **CBS_SORT** otomatik olarak liste kutusuna girilen dizeleri sıralar.  
  
-   **CBS_UPPERCASE** seçimi alanını ve listenin tüm metni büyük harfe dönüştürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC tarafından kullanılan stiller](../../mfc/reference/styles-used-by-mfc.md)   
 [CComboBox::Create] (ccombobox class.md #ccombobox__create   



