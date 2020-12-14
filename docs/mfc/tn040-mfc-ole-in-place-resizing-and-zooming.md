---
description: 'Daha fazla bilgi edinin: TN040: MFC/OLE In-Place yeniden boyutlandırma ve yakınlaştırma'
title: 'TN040: MFC-OLE In-Place yeniden boyutlandırma ve yakınlaştırma'
ms.date: 11/04/2016
helpviewer_keywords:
- resizing in-place
- TN040
- zooming and in-place activation
- in-place activation, zooming and resizing
ms.assetid: 4d7859bd-0b2e-4254-be62-2735cecf02c6
ms.openlocfilehash: e21b70dc10ee467f94386880255287218a3b6e99
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215397"
---
# <a name="tn040-mfcole-in-place-resizing-and-zooming"></a>TN040: MFC/OLE Yerinde Yeniden Boyutlandırma ve Yakınlaştırma

> [!NOTE]
> Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

Bu notta, yerinde düzenlemeyle ilgili sorunlar ve bir sunucunun doğru yakınlaştırmasını ve yerinde yeniden boyutlandırmayı nasıl gerçekleştirmesi gerektiği açıklanmaktadır. Yerinde etkinleştirme sayesinde, WYSıWYG kavramı, bu kapsayıcıların ve sunucuların birbirleriyle birlikte çalıştığı ve özellikle de OLE belirtimini aynı şekilde yorumladığı bir adım alınmıştır.

Bir kapsayıcı ve sunucu arasında yerinde etkinleştirmeyi destekleyen bir kapatma etkileşimi nedeniyle, son kullanıcıdan sürdürülmesi gereken birkaç beklentidir:

- Sunu görüntüsü ( `COleServerItem::OnDraw` geçersiz kılmada çizilen dosya), düzenlenmek üzere çizilekiyle tam olarak aynı görünmelidir (Bu, düzen araçlarının görünür olmaması dışında).

- Kapsayıcı yakınlaşdığınızda, sunucu penceresi de çok!

- Hem kapsayıcı hem de sunucu, aynı ölçümleri kullanarak nesneleri düzenlenmek üzere görüntülemelidir. Bu, görüntü cihazında oluşturma sırasında inç başına *mantıksal* piksel sayısı (inç başına fiziksel piksel) temelinde bir eşleme modu kullanılması anlamına gelir.

> [!NOTE]
> Yerinde etkinleştirme yalnızca katıştırılmış (bağlı değil) öğeler için geçerli olduğundan, yakınlaştırma yalnızca katıştırılmış nesneler için geçerlidir. Her ikisinde de, `COleServerDoc` `COleServerItem` Yakınlaştırma Için kullanılan API 'leri görürsünüz. Bu dichotomy 'in nedeni, yalnızca hem bağlantılı hem de katıştırılmış öğeler için geçerli olan işlevlerin de `COleServerItem` (Bu, ortak bir uygulamaya sahip olmasını sağlar) ve yalnızca katıştırılmış nesneler için geçerli olan işlevlerin `COleServerDoc` sınıfta (sunucu açısından perspektifinden, katıştırılmış olan **belgedir** ) bulunduğu işlevlerdir.

En fazla yük, sunucunun kapsayıcının yakınlaştırma faktöründe haberdar olması ve kendi düzen arabirimini uygun şekilde değiştirmesi için sunucu uygulayıcısı üzerine yerleştirilir. Ancak sunucu, kapsayıcının kullandığı yakınlaştırma faktörünü nasıl belirleyeceğini

## <a name="mfc-support-for-zooming"></a>Yakınlaştırma için MFC desteği

Geçerli yakınlaştırma faktörü çağırarak belirlenebilir `COleServerDoc::GetZoomFactor` . Belge yerinde etkin olmadığında bunu çağırmak, her zaman %100 yakınlaştırma faktörüne (veya 1:1 oranına) neden olur. Yerinde etkin iken çağırma, %100 dışında bir şey döndürebilir.

Doğru yakınlaştırma örneği için bkz. MFC OLE örnek [Hiersvr](../overview/visual-cpp-samples.md). HIERSVR 'nin yakınlaştırilmesi, metni gösterdiği ve genel olarak metinlerin doğrusal bir biçimde ölçeklendirilmesini (ipuçları, tipografik kurallar, tasarım genişlikleri ve yükseklikleri her ne kadar karmaşık bir şekilde karmaşıklaştırır) karmaşıktır. Yine de, HIERSVR, yakınlaştırmanın doğru bir şekilde uygulanması için makul bir başvurudur ve MFC öğreticisi [karalama](../overview/visual-cpp-samples.md) (adım 7).

`COleServerDoc::GetZoomFactor` kapsayıcıdan ya da `COleServerItem` ve sınıflarınızın uygulamasından erişilebilen farklı ölçümlere göre yakınlaştırma faktörünü belirler `COleServerDoc` . Kısacası, geçerli yakınlaştırma faktörü aşağıdaki formül tarafından belirlenir:

```
Position Rectangle (PR) / Container Extent (CE)
```

Konum DIKDÖRTGENI kapsayıcı tarafından belirlenir. Çağrıldığında, yerinde etkinleştirme sırasında sunucusuna döndürülür `COleClientItem::OnGetItemPosition` ve kapsayıcı sunucu ' a çağrı yaptığı zaman güncelleştirilir `COleServerDoc::OnSetItemRects` `COleClientItem::SetItemRects` .

KAPSAYıCı KAPSAMı, hesaplamak biraz daha karmaşıktır. Kapsayıcı çağrılırsa `COleServerItem::OnSetExtent` (öğesine çağrısıyla `COleClientItem::SetExtent` ), kapsayıcı kapsamı bu değer, mantıksal inç başına piksel sayısına göre piksellere dönüştürülür. Kapsayıcıda SetExtent (genellikle durum) çağrıldıysa KAPSAYıCı KAPSAMı, öğesinden döndürülen boyuttadır `COleServerItem::OnGetExtent` . Bu nedenle, kapsayıcı SetExtent olarak adlandırılmışsa, çerçeve kapsayıcının bunu doğal uzantının %100 ' i (öğesinden döndürülen değer) olarak adlandırdığını kabul eder `COleServerItem::GetExtent` . Başka bir şekilde ifade edilen çerçeve, kapsayıcının %100 (daha fazla değil, daha az değil) öğe olduğunu varsayar.

`COleServerItem::OnSetExtent` `COleServerItem::OnGetExtent` Benzer adlara sahip olsa da, aynı ada sahip olsa da, öğenin aynı özniteliğini işlemediklerinden emin olmak önemlidir. `OnSetExtent` , sunucunun nesnenin ne kadarının kapsayıcıda görünür olduğunu (yakınlaştırma etmeninden bağımsız olarak) bilmesini sağlamak için çağrılır ve `OnGetExtent` nesnenin ideal boyutunu belirlemede kapsayıcı tarafından çağırılır.

İlgili API 'lerin her birine bakarak daha net bir resim edinebilirsiniz:

## <a name="coleserveritemongetextent"></a>Cotaserverıtem:: OnGetExtent

Bu işlev, öğenin HIMETRIK birimlerinde "doğal boyut" değerini döndürmelidir. "Doğal boyut" i düşünmenin en iyi yolu, yazdırıldığında görünebilecek boyut olarak tanımlamaktır. Burada döndürülen boyut, belirli bir öğe içeriği (örneğin, belirli bir öğe için sabit olan meta dosyası gibi) için sabittir. Öğeye yakınlaştırma uygulandığında bu boyut değişmez. Bu, genellikle kapsayıcıyı çağırarak öğeyi daha fazla veya daha az alana verdiği zaman değişmez `OnSetExtent` . Değişikliğin bir örneği, kapsayıcı tarafından gönderilen son uzantı temelinde Sarmalanan metnin "kenar boşluğu" özelliği olmayan bir basit metin düzenleyicisine ait olabilir. Sunucu değişmezse, sunucu büyük olasılıkla sistem kayıt defterinde OLEMISC_RECOMPOSEONRESIZE bitini ayarlamış olmalıdır (Bu seçenek hakkında daha fazla bilgi için OLE SDK belgelerine bakın).

## <a name="coleserveritemonsetextent"></a>Cotaserverıtem:: OnSetExtent

Bu işlev, kapsayıcının nesnenin "daha fazla veya daha az" gösterdiği zaman çağrılır. Çoğu kapsayıcı bunu hiç çağırmaz. Varsayılan uygulama, `COleServerDoc::GetZoomFactor` yukarıda AÇıKLANAN KAPSAYıCı uzantısı değeri hesaplanırken içinde kullanılan ' m_sizeExtent ' içinde kapsayıcıdan alınan son değeri depolar.

## <a name="coleserverdoconsetitemrects"></a>Cotaserverdoc:: OnSetItemRects

Bu işlev yalnızca belge yerinde etkin olduğunda çağrılır. Kapsayıcı öğenin konumunu ya da öğeye uygulanan kırpmayı güncelleştirdiğinde çağrılır. Yukarıda açıklanan konum DIKDÖRTGENI, yakınlaştırma faktörü hesaplamasının payı sağlar. Sunucu, öğesini çağırarak öğe konumunun değiştirilmesini isteyebilir `COleServerDoc::RequestPositionChange` . Kapsayıcı, çağırarak `OnSetItemRects` (öğesine çağrısıyla) Bu isteğe yanıt verebilir veya yanıt vermeyebilir `COleServerItem::SetItemRects` .

## <a name="coleserverdocondraw"></a>Cotaserverdoc:: OnDraw

Geçersiz kılınarak oluşturulan meta dosyası, `COleServerItem::OnDraw` geçerli yakınlaştırma faktörüne bakılmaksızın tam olarak aynı meta dosyası üretir. Kapsayıcı, meta dosyası uygun şekilde ölçeklendirecektir. Bu, görünümün `OnDraw` ve sunucu öğesinin ' i arasındaki önemli bir ayrımdır `OnDraw` . Görünüm, yakınlaştırma işler, öğe yalnızca bir *Zoomable* meta dosyası oluşturuyor ve uygun yakınlaştırma yapmak için kapsayıcıyı kapsayıcıya bırakıyor.

Sunucunuzun doğru şekilde davranmasının en iyi yolu, `COleServerDoc::GetZoomFactor` belgenizin yerinde etkin olması durumunda öğesinin uygulamasını kullanmaktır.

## <a name="mfc-support-for-in-place-resizing"></a>In-Place yeniden boyutlandırma için MFC desteği

MFC, OLE 2 belirtiminde açıklandığı gibi yerinde yeniden boyutlandırma arabirimini tamamen uygular. Kullanıcı arabirimi, sınıfı tarafından desteklenir `COleResizeBar` , özel bir ileti WM_SIZECHILD ve bu iletinin ' de özel olarak işlenmesini destekler `COleIPFrameWnd` .

Bu iletinin, Framework tarafından sağlandıkından farklı işlemesini uygulamak isteyebilirsiniz. Yukarıda açıklandığı gibi, çerçeve kapsayıcıya kadar yerinde yeniden boyutlandırmanın sonuçlarını bırakır — sunucu, yakınlaştırma faktöründe değişikliğe yanıt verir. Kapsayıcı, (bir çağrının sonucu olarak çağrılır) işlemi sırasında hem KAPSAYıCı KAPSAMı hem de konum DIKDÖRTGENI ayarlanarak yeniden hareket eder, `COleClientItem::OnChangeItemPosition` `COleServerDoc::RequestPositionChange` sonra yerinde yeniden boyutlandırma, düzen penceresindeki öğenin "daha fazla veya daha az" gösterilmesi sonucunu verir. Kapsayıcı, yalnızca işlem sırasında konum DIKDÖRTGENI ayarlanarak yeniden hareket eder `COleClientItem::OnChangeItemPosition` , yakınlaştırma faktörü değişir ve öğe "Yakınlaştırılıp büyütülecektir" olarak gösterilir.

Bir sunucu, bu anlaşma sırasında ne olduğunu denetleyebilir (bir ölçüde daha fazla). Örneğin, bir elektronik tablo, Kullanıcı bir öğeyi yerinde düzenlenirken pencereyi yeniden boyutlandırdığında daha fazla veya daha az hücre göstermeyi tercih edebilir. Bir sözcük işlemcisi, pencereyle aynı olacak şekilde "sayfa kenar boşluklarını" değiştirmeyi ve metni yeni kenar boşluğuna yeniden sarmalaması için tercih edebilir. Sunucu, yeniden boyutlandırma işlemi tamamlandığında doğal kapsamı (öğesinden döndürülen boyut) değiştirerek bunu uygular `COleServerItem::OnGetExtent` . Bu, hem konum DIKDÖRTGENININ hem de KAPSAYıCı KAPSAMıNıN aynı miktarda değişmesine neden olur. Bu, aynı yakınlaştırma faktörüne, ancak daha büyük veya daha küçük bir görüntüleme alanına yol açar. Ayrıca, belgenin daha fazla veya daha az tarafından oluşturulan meta dosya görünür `OnDraw` . Bu durumda, yalnızca görüntüleme alanı yerine kullanıcı öğeyi yeniden boyutlandırdığında belgenin kendisi değişmekte olur.

Özel yeniden boyutlandırmayı uygulayabilir ve `COleResizeBar` sınıfınızın WM_SIZECHILD iletisini geçersiz kılarak tarafından belirtilen kullanıcı arabiriminden faydalanabilir `COleIPFrameWnd` . WM_SIZECHILD özellikleri hakkında daha fazla bilgi için bkz. [teknik notta 24](../mfc/tn024-mfc-defined-messages-and-resources.md).

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
