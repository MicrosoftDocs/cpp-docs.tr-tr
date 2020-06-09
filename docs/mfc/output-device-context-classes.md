---
title: Çıktı (Cihaz Bağlamı) Sınıfları
ms.date: 11/04/2016
f1_keywords:
- vc.classes.output
helpviewer_keywords:
- device contexts [MFC], classes
- screen output classes [MFC]
- printing classes [MFC]
- window drawing classes [MFC]
- painting classes [MFC]
- output classes [MFC]
ms.assetid: 35fd6435-a38e-42c6-a3fa-cd6f39370fc3
ms.openlocfilehash: b15f5034604f9d6b67574288140b79b144692478
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615356"
---
# <a name="output-device-context-classes"></a>Çıktı (Cihaz Bağlamı) Sınıfları

Bu sınıflar, Windows 'da bulunan farklı cihaz bağlamlarının türlerini kapsülleyebilirsiniz.

Aşağıdaki sınıfların çoğu bir Windows cihaz bağlamına yönelik bir tanıtıcıyı kapsülleyin. Cihaz bağlamı, bir cihazın görüntü veya yazıcı gibi çizim öznitelikleri hakkında bilgi içeren bir Windows nesnesidir. Tüm çizim çağrıları bir cihaz bağlamı nesnesi aracılığıyla yapılır. `CDC`Windows meta dosyaları için destek de dahil olmak üzere, özel cihaz bağlamı işlevselliğini kapsülten türetilmiş ek sınıflar.

[CDC](reference/cdc-class.md)<br/>
Cihaz bağlamları için temel sınıf. Tüm ekranda erişmek ve yazıcılar gibi görüntüleme bağlamlarına erişmek için doğrudan kullanılır.

[CPaintDC](reference/cpaintdc-class.md)<br/>
`OnPaint`Windows 'un üye işlevlerinde kullanılan bir görüntüleme bağlamı. `BeginPaint`Oluşturma ve yok etme üzerinde otomatik olarak çağırır `EndPaint` .

[CClientDC](reference/cclientdc-class.md)<br/>
Windows 'un istemci alanlarının görüntüleme bağlamı. Örneğin, fare olaylarına anında yanıt çekmek için kullanılır.

[CWindowDC](reference/cwindowdc-class.md)<br/>
Tüm Windows için, hem istemci hem de istemci olmayan alanların bulunduğu bir görüntüleme bağlamı.

[CMetaFileDC](reference/cmetafiledc-class.md)<br/>
Windows meta dosyaları için bir cihaz bağlamı. Windows meta dosyası, bir görüntü oluşturmak için yeniden yürütülebilecek bir grafik cihaz arabirimi (GDI) komutları dizisi içerir. Öğesinin üye işlevlerine yapılan çağrılar `CMetaFileDC` bir meta dosyasına kaydedilir.

## <a name="related-classes"></a>İlgili sınıflar

[CPoint](../atl-mfc-shared/reference/cpoint-class.md)<br/>
Koordinat (x, y) çiftlerini barındırır.

[CSize](../atl-mfc-shared/reference/csize-class.md)<br/>
Uzaklığı, göreli konumları veya eşleştirilmiş değerleri tutar.

[CRect](../atl-mfc-shared/reference/crect-class.md)<br/>
Dikdörtgen alanların koordinatlarını tutar.

[CRgn](reference/crgn-class.md)<br/>
Bir pencere içindeki elips, çokgen veya düzensiz bir alanı değiştirmek için bir GDI bölgesini kapsüller. Sınıfında kırpma üye işlevleriyle birlikte kullanılır `CDC` .

[CRectTracker](reference/crecttracker-class.md)<br/>
Dikdörtgen nesneleri yeniden boyutlandırmak ve taşımak için Kullanıcı arabirimini görüntüler ve işler.

[CColorDialog](reference/ccolordialog-class.md)<br/>
Renk seçmek için standart bir iletişim kutusu sağlar.

[CFontDialog](reference/cfontdialog-class.md)<br/>
Yazı tipi seçmek için standart bir iletişim kutusu sağlar.

[CPrintDialog](reference/cprintdialog-class.md)<br/>
Dosya yazdırmak için standart bir iletişim kutusu sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](class-library-overview.md)
