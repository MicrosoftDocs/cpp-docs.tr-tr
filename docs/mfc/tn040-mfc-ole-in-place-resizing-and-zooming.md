---
title: 'TN040: MFC-OLE yerinde yeniden boyutlandırma ve yakınlaştırma'
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.ole
helpviewer_keywords:
- resizing in-place
- TN040
- zooming and in-place activation
- in-place activation, zooming and resizing
ms.assetid: 4d7859bd-0b2e-4254-be62-2735cecf02c6
ms.openlocfilehash: c2cb25388184ac969bec7c01d8077a458c03a03a
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58775289"
---
# <a name="tn040-mfcole-in-place-resizing-and-zooming"></a>TN040: MFC/OLE yerinde yeniden boyutlandırma ve yakınlaştırma

> [!NOTE]
>  Aşağıdaki Teknik Not çevrimiçi belgelere ilk eklenmiştir beri güncelleştirilmemiş. Eski veya yanlış sonuç olarak, bazı yordamlar ve konular olabilir. En son bilgiler için bu konuyu çevrimiçi belge dizininde arama önerilir.

Bu Not, yerinde düzenleme için ilgili sorunları ve bir sunucu doğru yakınlaştırma gerçekleştirmek ve bunları nasıl yerinde yeniden boyutlandırma ele alınacaktır. Yerinde etkinleştirme WYSIWYG kavramı kapsayıcıların içinde bir adım daha ileri alınır ve sunucuları birbiriyle iş Birliği ve özellikle çok OLE belirtiminde aynı şekilde yorumlayabilir.

Bir kapsayıcı ve yerinde etkinleştirme destekleyen sunucusu arasındaki Kapat etkileşim nedeniyle bir dizi öğesinden saklanması gereken son kullanıcı beklentileri vardır:

- Sunu görüntüleme (çizilmiş meta `COleServerItem::OnDraw` geçersiz kılmak) tam olarak aynı zaman dışında (düzenleme araçlarını görünmez) düzenleme için çizildiğinde olarak görünmelidir.

- Kapsayıcı yakınlaştırır, sunucu penceresi çok gerekir!

- Nesneleri aynı ölçümleri kullanarak düzenlemek için kapsayıcı ve sunucu görüntülemelidir. Yani sayısına göre bir eşleme modunu kullanarak *mantıksal* inç başına piksel — görüntü cihazında işlenirken inç başına fiziksel piksel.

> [!NOTE]
>  Yerinde etkinleştirme yalnızca (bağlı değil) katıştırılmış öğeleri için geçerli olduğundan, yakınlaştırma katıştırılmış nesnelere yalnızca uygulanır. Her ikisinde de API görürsünüz `COleServerDoc` ve `COleServerItem` yakınlaştırma için kullanılır. Hem bağlantılı hem de katıştırılmış öğeler için geçerli olan işlevler olduğundan bu dichotomy sebebi `COleServerItem` (Bu, sık kullanılan bir uygulamasını olmasını sağlar) ve yalnızca katıştırılmış nesneler için geçerli olan işlevler yerleştirilir `COleServerDoc` sınıf (sunucunun açısından olduğu **belge** hangi gömüldüğü).

Yük çoğunu sunucu kapsayıcının yakınlaştırma faktörünü unutmayın ve düzenleme arabirimiyle uygun şekilde değiştirmek sunucu uygulayan üzerinde yerleştirilir. Ancak sunucu kapsayıcısı kullanarak yakınlaştırma faktörünü nasıl belirliyor

## <a name="mfc-support-for-zooming"></a>Yakınlaştırma için MFC desteği

Geçerli yakınlaştırma faktörünü çağırarak belirlenebilir `COleServerDoc::GetZoomFactor`. Belge yerinde etkin olmadığında bu çağrı, her zaman bir % 100 yakınlaştırma faktörünü (veya 1:1 oranını) sonuçlanır. Yerinde etkin % 100'dışında bir şey döndürebilir sırasında bunu çağırma.

MFC OLE örnek doğru yakınlaştırma örneği için bkz. [HIERSVR](../overview/visual-cpp-samples.md). Metni görüntüler ve metin, genel olarak, doğrusal bir şekilde (ipuçları, tipografi kuralları, tasarım genişlikleri ve karmaşık olursa olsun tüm yüksekliklerini) ölçeklenmez olarak HIERSVR içinde yakınlaştırma karmaşık. Yine de HIERSVR doğru yakınlaştırma uygulamak için makul bir başvuru ve bu nedenle MFC öğreticidir [KARALAMA](../overview/visual-cpp-samples.md) (7. adım).

`COleServerDoc::GetZoomFactor` Yakınlaştırma faktörünü farklı mevcut olan ölçümler kapsayıcısından veya uygulanması sayısına göre belirler, `COleServerItem` ve `COleServerDoc` sınıfları. Kısacası, geçerli yakınlaştırma faktörünü aşağıdaki formül tarafından belirlenir:

```
Position Rectangle (PR) / Container Extent (CE)
```

Konum DİKDÖRTGEN kapsayıcı tarafından belirlenir. Yerinde etkinleştirme sırasında bu sunucuya döndürülür olduğunda `COleClientItem::OnGetItemPosition` olarak adlandırılır ve kapsayıcı sunucunun çağırdığında güncelleştirilir `COleServerDoc::OnSetItemRects` (çağrısıyla `COleClientItem::SetItemRects`).

KAPSAYICI ölçüde hesaplamak için biraz daha karmaşıktır. Kapsayıcı çağrılırsa `COleServerItem::OnSetExtent` (çağrısıyla `COleClientItem::SetExtent`), KAPSAYICI ölçüde mantıksal inç başına piksel göre piksel dönüştürülen bu değeridir. Kapsayıcı (Bu genellikle böyledir) SetExtent çağırmadı sonra KAPSAYICI ölçüde döndürüldüğü boyutudur `COleServerItem::OnGetExtent`. Kapsayıcı SetExtent çağırmadı, bu nedenle, framework olsaydı kapsayıcı, doğal kapsamın %100 çağrısı yapmanız, olduğunu varsayar (döndürülen değer `COleServerItem::GetExtent`). Başka bir deyişle, belirtilen kapsayıcı öğenin %100 (daha fazla, az) görüntülüyor framework varsayar.

Ancak dikkat etmeniz önemlidir `COleServerItem::OnSetExtent` ve `COleServerItem::OnGetExtent` benzer adlara sahip aynı öğenin özniteliğini değiştirmek değil. `OnSetExtent` nesnenin ne kadar (bağımsız olarak yakınlaştırma faktörünü) kapsayıcısında görünür olduğunu biliyorsanız sunucu izin vermek için çağrılır ve `OnGetExtent` ideal bir nesnenin boyutunu belirlemek için kapsayıcı tarafından çağrılır.

Her biri ilgili API'leri bakarak NET bir resim elde edebilirsiniz:

## <a name="coleserveritemongetextent"></a>COleServerItem::OnGetExtent

Bu işlev "doğal boyutu" öğesi HIMETRIC birimleri cinsinden döndürmelidir. "Doğal boyutu" düşünmenin en iyi yolu, onu yazdırıldığında görünebilir boyutu tanımlamaktır. Burada döndürülen boyutla bir belirli öğe içeriği (çok belirli bir öğe için sabit meta dosyası gibi) için sabittir. Yakınlaştırma öğesine uygulandığında, bu boyut değişmez. Kapsayıcı öğe daha fazla veya daha az boş alan çağırarak verdiğinde genellikle değişmez `OnSetExtent`. Bir değişiklik örneği, bir basit metin düzenleyicisi kapsayıcı tarafından gönderilen son ölçüde göre metin sarılan yok "kenar boşluğu" özelliğine sahip olabilir. Bir sunucu değiştirirseniz, bu sunucunun sistem kayıt defterinde bit OLEMISC_RECOMPOSEONRESIZE büyük olasılıkla ayarlamanız gerekir (Bu seçenek hakkında daha fazla bilgi OLE SDK belgelerine bakın).

## <a name="coleserveritemonsetextent"></a>COleServerItem::OnSetExtent

Kapsayıcı "daha az veya" nesne gösterdiği durumlarda bu işlev çağrılır. Çoğu kapsayıcıları bu hiç çağırmayacaktır. Varsayılan uygulamada kullanılan 'm_sizeExtent' kapsayıcısında alınan son değeri depolar `COleServerDoc::GetZoomFactor` yukarıda açıklanan KAPSAYICI kapsam değeri hesaplanırken.

## <a name="coleserverdoconsetitemrects"></a>COleServerDoc::OnSetItemRects

Yalnızca belgenin yerinde etkin olduğunda bu işlev çağrılır. Kapsayıcı öğenin konumunu veya öğeye uygulanan kırpma güncelleştirildiğinde çağrılır. Konum DİKDÖRTGEN, yukarıda açıklandığı gibi yakınlaştırma faktörünü hesaplama için pay sağlar. Bir sunucu öğesi konumu çağırarak değiştirilmesi isteği `COleServerDoc::RequestPositionChange`. Kapsayıcı olabilir ya da çağırarak bu istek için yanıt vermeyebilir `OnSetItemRects` (çağrısıyla `COleServerItem::SetItemRects`).

## <a name="coleserverdocondraw"></a>COleServerDoc::OnDraw

Meta dosyası, geçersiz kılma tarafından oluşturulan bilmeniz önemlidir `COleServerItem::OnDraw` bakılmaksızın geçerli yakınlaştırma faktörünü tam olarak aynı meta üretir. Kapsayıcı meta uygun şekilde ölçeklendirir. Görünüm arasında önemli bir fark budur `OnDraw` ve sunucu öğenin `OnDraw`. Yakınlaştırma görünümü tanıtıcıları öğenin yalnızca oluşturur bir *yakınlaştırılabilir* meta dosyası ve uygun yakınlaştırma yapmak için kapsayıcı kadar bırakır.

En iyi yolu, sunucunuzun düzgün şekilde davranan Sigortası uyarlamasını kullanmaktır `COleServerDoc::GetZoomFactor` belgenizi yerinde etkin ise.

## <a name="mfc-support-for-in-place-resizing"></a>Yerinde yeniden boyutlandırma için MFC desteği

MFC, OLE 2 Belirtimi'nde açıklanan yerinde yeniden boyutlandırma arabirimi tam olarak uygular. Kullanıcı arabirimi tarafından desteklenen `COleResizeBar` sınıfı, bir özel ileti WM_SIZECHILD ve bu iletiye özel işlenmesini `COleIPFrameWnd`.

Bu iletinin framework tarafından sağlanan değerinden farklı işleme uygulamak isteyebilirsiniz. Yukarıda açıklandığı gibi framework kadar kapsayıcı yerinde yeniden boyutlandırma sonuçlarını bırakır; yakınlaştırma faktörünü değiştirmeyi sunucu yanıt verir. Kapsayıcı hem ayarlayarak tepki verir, KAPSAYICI kapsamını ve konumu DİKDÖRTGEN işlenmesi sırasında kendi `COleClientItem::OnChangeItemPosition` (çağrı sonucunda adlı `COleServerDoc::RequestPositionChange`) sonra yerinde yeniden boyutlandırma düzenleme "fazla veya az" öğesinin gösterirken neden olur pencere. Kapsayıcı KONUMUNU DİKDÖRTGEN işlenmesi sırasında yalnızca ayarlayarak tepki verir durumunda `COleClientItem::OnChangeItemPosition`yakınlaştırma faktörünü değişir ve öğeyi "veya uzaklaştırılacağını." gösterilir.

Bir sunucu (dereceye kadar), bu anlaşması sırasında neler denetleyebilirsiniz. Elektronik tablo, örneğin seçmediğiniz kullanıcı pencere öğesi düzenlerken boyutlandırdığında az veya daha fazla hücre yerinde gösterilecek. Bir word-processor penceresi ile aynıdır ve metin yeni kenar boşluğuna yeniden sarmalamanız "kenar boşluklarını" değiştirmek seçmeniz. Hizmetleri uygulayan bu doğal ölçüde değiştirerek (öğesinden döndürülen boyutla `COleServerItem::OnGetExtent`) ne zaman yeniden boyutlandırma gerçekleştirilir. Bu, aynı yakınlaştırma faktörünü, ancak daha büyük bir kaynaklanan ya da daha küçük görüntüleme alanının aynı miktarda değiştirmek için KAPSAYICI ölçüde ve konumu DİKDÖRTGEN neden olur. Ayrıca, daha az veya belgenin tarafından oluşturulan meta dosyası içinde görünür olacak `OnDraw`. Bu durumda, yalnızca görüntüleme alanı yerine bir öğenin kullanıcı yeniden boyutlandırdığında belge değişiyor.

Özel yeniden boyutlandırma uygular ve hala tarafından sağlanan kullanıcı arabirimi yararlanarak `COleResizeBar` WM_SIZECHILD iletisinde kılarak, `COleIPFrameWnd` sınıfı. WM_SIZECHILD özellikleri hakkında daha fazla bilgi için bkz. [Teknik Not 24](../mfc/tn024-mfc-defined-messages-and-resources.md).

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
