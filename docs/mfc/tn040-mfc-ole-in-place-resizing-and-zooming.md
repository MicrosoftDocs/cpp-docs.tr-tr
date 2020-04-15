---
title: 'TN040: MFC-OLE Yerinde Boyutlandırma ve Yakınlaştırma'
ms.date: 11/04/2016
helpviewer_keywords:
- resizing in-place
- TN040
- zooming and in-place activation
- in-place activation, zooming and resizing
ms.assetid: 4d7859bd-0b2e-4254-be62-2735cecf02c6
ms.openlocfilehash: 65f9ef04c9740e8e6f0a8e72d9d6c39008198755
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372160"
---
# <a name="tn040-mfcole-in-place-resizing-and-zooming"></a>TN040: MFC/OLE Yerinde Yeniden Boyutlandırma ve Yakınlaştırma

> [!NOTE]
> Aşağıdaki teknik not, çevrimiçi belgelere ilk olarak eklenmediğinden beri güncelleştirilemedi. Sonuç olarak, bazı yordamlar ve konular güncel veya yanlış olabilir. En son bilgiler için, çevrimiçi belge dizini ilgi alanı için arama nız önerilir.

Bu notta, yerinde düzenlemeyle ilgili sorunlar ve bir sunucunun doğru yakınlaştırma ve yerinde yeniden boyutlandırmayı nasıl gerçekleştirmesi gerektiği tartışılır. Yerinde etkinleştirme ile, WYSIWYG kavramı konteyner ve sunucular birbirleriyle işbirliği bir adım daha ileri alınır ve özellikle çok aynı şekilde OLE belirtimi yorumlamak.

Yerinde etkinleştirme destekleyen bir kapsayıcı ve sunucu arasındaki yakın etkileşim nedeniyle, son kullanıcıdan korunması gereken bir dizi beklenti vardır:

- Sunu ekranı `COleServerItem::OnDraw` (geçersiz kılmada çizilen metadosya) düzenleme için çizildiğindekiyle tam olarak aynı görünmelidir (düzenleme araçlarının görünmemesi dışında).

- Kapsayıcı yakınlaştırır, sunucu penceresi de gerekir!

- Hem kapsayıcı hem de sunucu, aynı ölçümleri kullanarak düzenleme için nesneleri görüntülemelidir. Bu, görüntü aygıtında görüntülenirken inç başına fiziksel piksel değil, inç başına *mantıksal* piksel sayısına dayalı bir eşleme modu kullanmak anlamına gelir.

> [!NOTE]
> Yerinde etkinleştirme yalnızca katıştırılmış (bağlı olmayan) öğeler için geçerli olduğundan, yakınlaştırma yalnızca katıştırılmış nesneler için geçerlidir. Her ikisinde de `COleServerDoc` API'ler göreceksiniz ve `COleServerItem` bu yakınlaştırma için kullanılır. Bu ikilemin nedeni, yalnızca bağlantılı ve katıştırılmış öğeler için `COleServerItem` geçerli olan işlevlerin içinde olması (bu ortak bir uygulamaya sahip olmak için `COleServerDoc` izin verir) ve yalnızca katıştırılmış nesneler için geçerli olan işlevler sınıfta yer alır (sunucunun bakış açısından, gömülü **belgedir).**

Yükün çoğu sunucu uygulayıcısına yerleştirilir, bu da sunucunun kapsayıcının yakınlaştırma faktöründen haberdar olması ve düzenleme arabirimini uygun şekilde değiştirmesi gerekir. Ancak sunucu, kapsayıcının kullandığı yakınlaştırma faktörlerini nasıl belirler?

## <a name="mfc-support-for-zooming"></a>Yakınlaştırma için MFC Desteği

Geçerli yakınlaştırma faktörü arayarak `COleServerDoc::GetZoomFactor`belirlenebilir. Belge yerinde etkin olmadığında bunu çağırmak her zaman %100 yakınlaştırma faktörüne (veya 1:1 oranına) neden olur. Yerinde etkinken aramak %100'den başka bir şeyi döndürebilir.

Doğru yakınlaştırma örneği için MFC OLE örnek [HIERSVR](../overview/visual-cpp-samples.md)bakın. HIERSVR'da yakınlaştırma, metni görüntülemesi ve genel olarak metnin doğrusal bir şekilde ölçeklenmemesi (ipuçları, tipografik kurallar, tasarım genişlikleri ve yüksekliklerin tüm bunları karmaşıklaştırması) karmaşıktır. Yine de, HIERSVR doğru yakınlaştırma uygulamak için makul bir referans, ve böylece MFC Tutorial [SCRIBBLE](../overview/visual-cpp-samples.md) (adım 7) olduğunu.

`COleServerDoc::GetZoomFactor`kapsayıcıdan veya sizin `COleServerItem` ve `COleServerDoc` sınıfların uygulanmasından elde edilebilen bir dizi farklı ölçüme göre yakınlaştırma faktörünün belirlenmesini sağlar. Kısacası, geçerli yakınlaştırma faktörü aşağıdaki formülle belirlenir:

```
Position Rectangle (PR) / Container Extent (CE)
```

POZİsYON DİKDAĞI konteyner tarafından belirlenir. Çağrıldığında `COleClientItem::OnGetItemPosition` yerinde etkinleştirme sırasında sunucuya döndürülür ve kapsayıcı sunucunun sunucuyu aradığında güncelleştirilir `COleServerDoc::OnSetItemRects` (bir çağrı `COleClientItem::SetItemRects`ile).

KONTEYNER ÖLÇÜDE hesaplamak için biraz daha karmaşıktır. Kapsayıcı aradıysa `COleServerItem::OnSetExtent` (bir çağrı `COleClientItem::SetExtent`ile), o zaman KONTEYNER ÖLÇÜDE bu değer piksel için mantıksal inç başına piksel sayısına göre dönüştürülür. Kapsayıcı SetExtent (genellikle böyledir) olarak adlandırılmazsa, KONTEYNER ÖLÇÜDE'den `COleServerItem::OnGetExtent`döndürülen boyutdur. Bu nedenle, kapsayıcı SetExtent olarak adlandırılmazsa, çerçeve, eğer yapsaydı, kapsayıcının onu doğal boyutun %100'ü (döndürülen `COleServerItem::GetExtent`değer) ile çağıracağını varsayar. Başka bir şekilde belirtildiği gibi, çerçeve kapsayıcı öğenin% 100 (daha fazla, daha az) görüntüleniyor varsayar.

Bu rağmen `COleServerItem::OnSetExtent` ve `COleServerItem::OnGetExtent` benzer adlara sahip, onlar öğenin aynı özniteliği işlemek olmadığını unutmayın. `OnSetExtent`sunucuya, nesnenin ne kadarının kapsayıcıda görünür olduğunu (yakınlaştırma faktörüne `OnGetExtent` bakılmaksızın) bildirmek için çağrılır ve nesnenin ideal boyutunu belirlemek için kapsayıcı tarafından çağrılır.

İlgili API'lerin her birine bakarak daha net bir resim elde edebilirsiniz:

## <a name="coleserveritemongetextent"></a>COleServerItem::OnGetExtent

Bu işlev, maddenin HIMETRIC birimlerindeki "doğal boyutu" döndürmelidir. "Doğal boyutu" düşünmenin en iyi yolu, yazdırıldığında görünebileceği boyut olarak tanımlamaktır. Burada döndürülen boyut belirli bir öğe içeriği için sabittir (belirli bir öğe için sabit olan metadosya gibi). Öğeye yakınlaştırma uygulandığında bu boyut değişmez. Kapsayıcı öğeyi arayarak `OnSetExtent`daha fazla veya daha az alan verdiğinde genellikle değişmez. Bir değişiklik örneği, kapsayıcı tarafından gönderilen son ölçüde bağlı olarak metni sarılmış hiçbir "kenar boşluğu" özelliği ile basit bir metin düzenleyicisi olabilir. Bir sunucu değişirse, sunucu büyük olasılıkla sistem kayıt defterinde OLEMISC_RECOMPOSEONRESIZE bitini ayarlamalıdır (bu seçenek hakkında daha fazla bilgi için OLE SDK belgelerine bakın).

## <a name="coleserveritemonsetextent"></a>COleServerItem::OnSetExtent

Kapsayıcı nesnenin "az veya çok" gösterir bu işlev denir. Çoğu konteyner bunu hiç aramaz. Varsayılan uygulama, yukarıda açıklanan KONTEYNER DEĞERİ `COleServerDoc::GetZoomFactor` hesaplanırken kullanılan 'm_sizeExtent' olarak kapsayıcıdan alınan son değeri depolar.

## <a name="coleserverdoconsetitemrects"></a>COleServerDoc::OnSetItemRects

Bu işlev yalnızca belge yerinde etkin olduğunda çağrılır. Kapsayıcı, öğenin konumunu veya öğeye uygulanan kırpma öğesini güncelleştirirse çağrılır. POSITION RECTANGLE, yukarıda da belirtildiği gibi, yakınlaştırma faktörü hesaplaması için sayı sağlar. Sunucu, öğe konumunun ' u `COleServerDoc::RequestPositionChange`arayarak değiştirilmesini isteyebilir. Kapsayıcı bu isteğe arayarak `OnSetItemRects` yanıt verebilir veya yanıt `COleServerItem::SetItemRects`vermeyebilir (bir çağrı ile).

## <a name="coleserverdocondraw"></a>COleServerDoc::OnDraw

Geçersiz kılma tarafından oluşturulan metadosya, geçerli `COleServerItem::OnDraw` yakınlaştırma faktörü ne olursa olsun, tam olarak aynı metadosya üretir gerçekleştirmek önemlidir. Kapsayıcı, metadosyayı uygun şekilde ölçeklendirecek. Bu, görünümün `OnDraw` ve sunucu `OnDraw`öğesinin. Görünüm yakınlaştırma yı işler, öğe sadece *yakınlaştırılabilir* bir metadosya oluşturur ve uygun yakınlaştırmayı yapmak için kapsayıcıya bırakır.

Sunucunuzun doğru şekilde durmasını sağlamanın en iyi yolu, `COleServerDoc::GetZoomFactor` belgenizin yerinde etkin olup olmadığının uygulanmasını kullanmaktır.

## <a name="mfc-support-for-in-place-resizing"></a>Yerinde Yeniden Boyutlandırma için MFC Desteği

MFC, OLE 2 belirtiminde açıklandığı gibi yerinde yeniden boyutlandırma arabirimini tam olarak uygular. Kullanıcı arabirimi `COleResizeBar` sınıf, özel bir ileti WM_SIZECHILD ve bu iletinin `COleIPFrameWnd`özel olarak işlenmesi tarafından desteklenir.

Bu iletinin çerçeve tarafından sağlanandan farklı şekilde işlenmesini uygulamak isteyebilirsiniz. Yukarıda açıklandığı gibi, çerçeve kapsayıcıya kadar yerinde yeniden boyutlandırma sonuçlarını bırakır - sunucu yakınlaştırma faktöründeki değişikliğe yanıt verir. Kapsayıcı, işlemini `COleClientItem::OnChangeItemPosition` sırasında hem KONTEYNER KAPSAMı'nı hem de KONUM DIKDÖRTGENini ayarlayarak tepki `COleServerDoc::RequestPositionChange`verirse (yapılan çağrı nın sonucu olarak adlandırılır) yerine yeniden boyutlandırma, düzenleme penceresinde öğenin "daha fazla veya daha az" gösterilmesine neden olur. Kapsayıcı işlemi sırasında KONUM DIKDÖRTGENi'ni ayarlayarak tepki `COleClientItem::OnChangeItemPosition`verirse, yakınlaştırma faktörü değişecek ve öğe "yakınlaştırılmış veya uzaklaştırılmış" olarak gösterilir.

Bir sunucu bu anlaşma sırasında ne olduğunu (bir dereceye kadar) denetleyebilir. Örneğin, kullanıcı öğeyi yerinde düzenlerken pencereyi yeniden boyutlandırdığında bir elektronik tablo daha fazla veya daha az hücre göstermeyi seçebilir. Bir sözcük işlemcisi pencereyle aynı olacak şekilde "sayfa kenar boşluklarını" değiştirmeyi seçebilir ve metni yeni kenar boşluğuna yeniden sarın. Sunucular, yeniden boyutlandırma yapıldığında doğal `COleServerItem::OnGetExtent`kapsamı (döndürülen boyut) değiştirerek bunu uygular. Bu, hem KONUM DIKDÖRTGENinin hem de KONTEYNER KAPSAMının aynı miktarda değişmesine ve aynı yakınlaştırma faktörüne, ancak daha büyük veya daha küçük bir görüntüleme alanına neden olur. Buna ek olarak, belgenin daha fazla veya daha `OnDraw`az tarafından oluşturulan metafile görünür olacaktır. Bu durumda, kullanıcı yalnızca görüntüleme alanı yerine öğeyi yeniden boyutlandırdığında belgenin kendisi değişiyor.

Özel yeniden boyutlandırma uygulayabilir ve sınıfınızdaki `COleResizeBar` WM_SIZECHILD iletiyi geçersiz `COleIPFrameWnd` kılarak sağlanan kullanıcı arabiriminden yararlanmaya devam edebilirsiniz. WM_SIZECHILD özellikleri hakkında daha fazla bilgi için [Teknik Not 24'e](../mfc/tn024-mfc-defined-messages-and-resources.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
