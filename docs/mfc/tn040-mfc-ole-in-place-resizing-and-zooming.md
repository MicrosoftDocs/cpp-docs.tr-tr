---
title: "TN040: MFC OLE yeniden boyutlandırma ve yakınlaştırma yerinde | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.ole
dev_langs: C++
helpviewer_keywords:
- resizing in-place
- TN040
- zooming and in-place activation
- in-place activation, zooming and resizing
ms.assetid: 4d7859bd-0b2e-4254-be62-2735cecf02c6
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b1113da01e58ec00cd4420aab4424b1c20e127e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="tn040-mfcole-in-place-resizing-and-zooming"></a>TN040: MFC/OLE Yerinde Yeniden Boyutlandırma ve Yakınlaştırma
> [!NOTE]
>  İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.  
  
 Bu Not yerinde düzenleme ile ilgili sorunları ve bir sunucu doğru yakınlaştırma gerçekleştirmek ve yerinde yeniden boyutlandırma ele alınacaktır. Yerinde etkinleştirme WYSIWYG kavramı bir adım bu kapsayıcılardaki alınır ve sunucuları birbirleri ile işbirliği yapar ve özellikle çok OLE belirtimi aynı şekilde yorumlayabilir.  
  
 Bir kapsayıcı ve yerinde etkinleştirme destekleyen sunucusu arasındaki Kapat etkileşim nedeniyle saklanması gereken son kullanıcı gelen beklentilerini sayısı vardır:  
  
-   Sunu görüntüleme (çizilmiş meta dosyası `COleServerItem::OnDraw` geçersiz kılmak) tam olarak aynı zaman (düzenleme araçları görünmez olduğunu dışında) düzenleme için çizildiğinde olarak görünmelidir.  
  
-   Kapsayıcı yakınlaştırır, sunucu penceresi çok gerekir!  
  
-   Aynı ölçümleri kullanarak düzenleme için nesneleri kapsayıcı ve sunucu görüntülemelidir. Sayısına göre bir eşleme modunu kullanarak yani *mantıksal* inç başına piksel — fiziksel inç başına piksel görüntü cihazında oluşturulurken,.  
  
> [!NOTE]
>  Yerinde etkinleştirme (bağlı değil) katıştırılmış öğeleri için yalnızca uygulandığından yakınlaştırma katıştırılmış nesnelere yalnızca uygulanır. İkisi de API'leri görürsünüz `COleServerDoc` ve `COleServerItem` yakınlaştırma için kullanılır. Bağlantılı ve katıştırılmış öğeleri için geçerli olan işlevler olduğundan bu dichotomy sebebi `COleServerItem` (Bu, yaygın olarak görülen bir uygulama bulunmasına izin verir) ve yalnızca katıştırılmış nesneler için geçerli olan işlevler içinde bulunur `COleServerDoc` sınıf (sunucunun açısından olduğu `document` katıştırılmış).  
  
 Yük çoğunu sunucu kapsayıcının yakınlaştırma faktörünü farkında olmalı ve düzenleme arabirimiyle uygun şekilde değiştirin, sunucu uygulayan üzerinde yerleştirilir. Ancak sunucu kapsayıcısı kullanarak yakınlaştırma faktörünü nasıl olmadığını belirler  
  
## <a name="mfc-support-for-zooming"></a>Yakınlaştırma için MFC desteği  
 Geçerli yakınlaştırma faktörünü çağırarak belirlenebilir `COleServerDoc::GetZoomFactor`. Belge yerinde etkin olmadığında bu çağırma her zaman bir % 100 yakınlaştırma faktörünü (veya 1:1 oranında) neden olur. Yerinde etkin % 100'den bir şey döndürebilir sırada çağrılıyor.  
  
 MFC OLE örnek doğru yakınlaştırma örneği için bkz: [HIERSVR](../visual-cpp-samples.md). Metni görüntüleyen ve doğrusal bir şekilde (ipuçlarını, tipografi kuralları, tasarım genişlikleri ve konuyu karmaşık hale yükseklikte tüm) metin, genel olarak, ölçeklenmez olarak HIERSVR içinde yakınlaştırma karmaşık. Yine de, HIERSVR doğru yakınlaştırma uygulamak için makul bir başvuru ve bu nedenle MFC öğretici [KARALAMA](../visual-cpp-samples.md) (adım 7).  
  
 `COleServerDoc::GetZoomFactor`farklı ölçümleri kullanılabilir kapsayıcısından veya uygulanması sayısına dayalı yakınlaştırma faktörünü belirler, `COleServerItem` ve `COleServerDoc` sınıfları. Kısacası, geçerli yakınlaştırma faktörünü aşağıdaki formülde belirlenir:  
  
```  
Position Rectangle (PR) / Container Extent (CE)  
```  
  
 Konum DİKDÖRTGEN kapsayıcı tarafından belirlenir. Yerinde etkinleştirme sırasında sunucuya döndürülür zaman `COleClientItem::OnGetItemPosition` olarak adlandırılır ve kapsayıcı sunucunun çağırdığında güncelleştirilmiş `COleServerDoc::OnSetItemRects` (çağrısıyla `COleClientItem::SetItemRects`).  
  
 KAPSAYICI ölçüde hesaplamak için biraz daha karmaşıktır. Kapsayıcı çağrıldıklarında `COleServerItem::OnSetExtent` (çağrısıyla `COleClientItem::SetExtent`), KAPSAYICI ölçüde mantıksal inç başına piksel sayısına dayalı piksel dönüştürülen bu değeri olur. Kapsayıcı (genellikle söz konusu olduğu) SetExtent çağırmadı sonra KAPSAYICI ölçüde döndürülen boyutudur `COleServerItem::OnGetExtent`. Kapsayıcı SetExtent çağırmadı sahipse, bu nedenle, framework olsaydı kapsayıcı % 100'ile doğal ölçüde adlı olduğunu varsayar (döndürülen değer **COleServerItem::GetExtent**). Başka bir yolu, belirtilen kapsayıcı öğenin % (artık, daha az) 100 görüntülüyor framework varsayar.  
  
 Ancak unutmayın önemlidir `COleServerItem::OnSetExtent` ve `COleServerItem::OnGetExtent` benzer adlara sahip aynı öznitelik öğenin işlemek değil. `OnSetExtent`nesnenin ne kadar kapsayıcısındaki (bağımsız olarak yakınlaştırma faktörünü) görünür olduğunu biliyorsanız sunucu izin vermek için çağrılır ve `OnGetExtent` nesnesinin ideal boyutunu belirlemek için kapsayıcı tarafından çağrılır.  
  
 Her ilgili API'leri bakarak NET bir resim elde edebilirsiniz:  
  
## <a name="coleserveritemongetextent"></a>COleServerItem::OnGetExtent  
 Bu işlev "doğal boyutu" öğesinin HIMETRIC birimlerinde döndürmelidir. "Doğal boyutu" düşünülecek iyi yazdırıldığında görünebilir boyutu tanımlamak için yoludur. Burada döndürülen boyut, bir maddeyi içeriği (çok belirli bir öğe için sabittir meta dosyası gibi) için sabittir. Yakınlaştırma öğesine uygulandığında bu boyutunu değiştirmez. Kapsayıcı öğe daha fazla veya az alan çağırarak verdiğinde genellikle değiştirmez `OnSetExtent`. Bir değişiklik örneği, basit bir metin düzenleyicisi kapsayıcı tarafından gönderilen son ölçüde göre metin kaydırılan yok "kenar boşluğu" özelliğine sahip olabilir. Bir sunucu değiştirirseniz, bu sunucunun sistem kayıt defterinde bit OLEMISC_RECOMPOSEONRESIZE büyük olasılıkla ayarlamanız gerekir (Bu seçenek hakkında daha fazla bilgi için OLE SDK belgelerine bakın).  
  
## <a name="coleserveritemonsetextent"></a>COleServerItem::OnSetExtent  
 Bu işlev, kapsayıcı "fazla veya az" nesnesinin gösterdiği durumlarda çağrılır. Çoğu kapsayıcıları bu hiç çağırmayacaktır. Varsayılan uygulaması içinde kullanılan 'm_sizeExtent' kapsayıcısında alınan son değerini depolar `COleServerDoc::GetZoomFactor` yukarıda açıklanan KAPSAYICI ölçüde değeri hesaplanırken.  
  
## <a name="coleserverdoconsetitemrects"></a>COleServerDoc::OnSetItemRects  
 Yalnızca belge yerinde etkin olduğunda bu işlev çağrılır. Kapsayıcı öğesi'nin konumu veya öğeye uygulanan kırpma güncelleştirildiğinde çağrılır. Konum DİKDÖRTGEN, yukarıda açıklanan şekilde pay yakınlaştırma faktörünü hesaplamasını sağlar. Bir sunucu öğe konumu çağırarak değiştirilmesi isteği `COleServerDoc::RequestPositionChange`. Kapsayıcı olabilir veya bu isteği çağırarak yanıt vermeyebilir `OnSetItemRects` (çağrısıyla **COleServerItem::SetItemRects**).  
  
## <a name="coleserverdocondraw"></a>COleServerDoc::OnDraw  
 Meta dosyası, geçersiz kılma tarafından oluşturulan bilmeniz önemlidir `COleServerItem::OnDraw` geçerli yakınlaştırma faktörünü bağımsız olarak tam olarak aynı meta üretir. Kapsayıcı meta dosyası uygun şekilde ölçeklendirir. Görünümün arasında önemli bir fark budur `OnDraw` ve sunucu öğesi'nin `OnDraw`. Yakınlaştırma görünümü tanıtıcıları öğesi yalnızca oluşturur bir *yakınlaştırılabilir* meta dosyası ve uygun yakınlaştırma yapmak için kapsayıcı kadar bırakır.  
  
 Sunucunuz düzgün şekilde davranan güvence altına almaya en iyi yolu uyarlamasını kullanmaktır `COleServerDoc::GetZoomFactor` belgenizi yerinde etkin ise.  
  
## <a name="mfc-support-for-in-place-resizing"></a>Yerinde yeniden boyutlandırma için MFC desteği  
 MFC tam olarak OLE 2 belirtiminde açıklandığı gibi yerinde yeniden boyutlandırma arabirimini uygular. Kullanıcı arabirimi tarafından desteklenen `COleResizeBar` sınıfı, özel bir ileti **WM_SIZECHILD**ve bu iletinin özel işleme `COleIPFrameWnd`.  
  
 Bu iletinin çerçevesi tarafından sağlanan daha farklı işleme uygulamak isteyebilirsiniz. Yukarıda açıklandığı gibi en fazla kapsayıcı yerinde yeniden boyutlandırma sonuçlarını framework bırakır — sunucu yakınlaştırma faktörünü değişikliği yanıt verir. Her ikisi de ayarlayarak kapsayıcı tepki verdiğini, KAPSAYICI kapsamını ve konumu DİKDÖRTGEN işlenmesi sırasında kendi `COleClientItem::OnChangeItemPosition` (yapılan bir çağrı sonucunda adlı `COleServerDoc::RequestPositionChange`) yerinde yeniden boyutlandırma düzenleme "fazla veya az" öğesinin gösterilmesine yol sonra penceresini açın. Kapsayıcı KONUMUNU DİKDÖRTGEN işlenmesi sırasında yalnızca ayarlayarak tepki verdiğini varsa `COleClientItem::OnChangeItemPosition`yakınlaştırma faktörünü değiştirin ve "veya uzaklaştırılacağını." öğe gösterilir  
  
 Bir sunucu (dereceye kadar) bu anlaşması sırasında neler kontrol edebilirsiniz. Elektronik tablo, örneğin seçmediğiniz kullanıcı öğesi düzenlenirken yeniden boyutlandırır yerinde az veya daha fazla hücre göstermek. Bir word-processor penceresi aynıdır ve metin yeni kenar boşluğuna yeniden kaydırması "Sayfa kenar boşluklarını" değiştirme bırakmayı. Sunucuları uygulamak bu doğal ölçüde değiştirerek (döndürülen boyutu `COleServerItem::OnGetExtent`) ne zaman yeniden boyutlandırma yapılır. Bu, aynı yakınlaştırma faktörünü, ancak daha büyük bir kaynaklanan ya da daha küçük görüntüleme alanında aynı miktarda değiştirmek için KAPSAYICI ölçüde ve konumu DİKDÖRTGEN neden olur. Ayrıca, daha az veya belgenin tarafından oluşturulan meta dosyası içinde görünür olacak `OnDraw`. Bu durumda, kullanıcı yalnızca görüntüleme alanı yerine öğeyi yeniden boyutlandırır zaman belge değiştiriyor.  
  
 Özel yeniden boyutlandırma uygulamak ve hala tarafından sağlanan kullanıcı arabirimi yararlanan `COleResizeBar` kılarak **WM_SIZECHILD** içinde ileti, `COleIPFrameWnd` sınıfı. Ayrıntılarını hakkında daha fazla bilgi için **WM_SIZECHILD**, bkz: [Teknik Not 24](../mfc/tn024-mfc-defined-messages-and-resources.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

