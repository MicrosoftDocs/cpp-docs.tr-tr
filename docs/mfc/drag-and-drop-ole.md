---
title: OLE sürükle ve bırak
description: Microsoft Foundation Sınıfları (MFC) OLE sürükle ve bırak, bırakma kaynağı uygulama, bırakma hedefi ve sürükleme ve bırakmayı özelleştirme hakkında genel bakış.
ms.date: 02/09/2020
helpviewer_keywords:
- OLE server applications [MFC], drag and drop
- drag and drop [MFC]
- OLE applications [MFC], drag and drop
- File Manager drag and drop support [MFC]
- drag and drop [MFC], about OLE drag and drop
- OLE drag and drop [MFC]
ms.assetid: a4595350-ca06-4400-88a1-f0175c76b77b
ms.openlocfilehash: 23680765377d325bdc1f8878daf4d4fc553a1304
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84623183"
---
# <a name="ole-drag-and-drop"></a>OLE sürükle ve bırak

OLE 'nin sürükle ve bırak özelliği öncelikle veri kopyalama ve yapıştırma için bir kısayoldur. Verileri kopyalamak veya yapıştırmak için panoyu kullandığınızda bir dizi adım gerekir. Verileri seçin ve Düzenle veya **Kopyala** ' yı seçerek **düzenleme** menüsünden **Kes** ' i seçin. Sonra hedef uygulamaya veya pencereye taşınır ve imleci hedef konuma yerleştirebilirsiniz. Son olarak, menüden **Edit**  >  **yapıştırmayı** Düzenle seçeneğini belirleyin.

OLE sürükle ve bırak özelliği dosya yöneticisi sürükleme ve bırakma mekanizmasından farklıdır. Dosya Yöneticisi yalnızca dosya adlarını işleyebilir ve dosya adlarını uygulamalara geçirmek için özel olarak tasarlanmıştır. OLE 'de sürükleyip bırakma çok daha genel. Panoya yerleştirilebilecek tüm verileri sürükleyip bırakmanıza olanak tanır.

OLE sürükle ve bırak kullandığınızda işlemden iki adımı kaldırırsınız. Kaynak pencereden ("bırakma kaynağı") verileri seçin, ardından hedefi hedefe sürükleyin ("bırakma hedefi"). Bunu, fare düğmesini bırakarak bırakmalısınız. İşlem, menüler gereksinimini ortadan kaldırır ve Kopyala/Yapıştır sırasından daha hızlıdır. Yalnızca bir gereksinim vardır: hem bırakma kaynağı hem de bırakma hedefinin açık olması ve ekranda en az kısmen görünür olması gerekir.

OLE sürükle ve bırak kullanarak, veriler bir konumdan diğerine kolayca aktarılabilir: bir belge Içinde, farklı belgeler arasında veya uygulamalar arasında. Bir kapsayıcı veya sunucu uygulamasında uygulanabilir. Herhangi bir uygulama bir bırakma kaynağı, bir bırakma hedefi veya her ikisi olabilir. Bir uygulama hem kaynak bırakma hem de bırakma hedefi desteğini uygularsa, alt pencereler arasında veya bir pencere içinde sürükleyip bırakabilirsiniz. Bu özellik, uygulamanızın kullanımını çok daha kolay hale getirir.

[Veri nesneleri ve veri kaynakları (OLE)](data-objects-and-data-sources-ole.md) makalelerinde, uygulamalarınızda veri aktarımının nasıl uygulanacağı açıklanmaktadır. MFC OLE örnekleri [Oclient](../overview/visual-cpp-samples.md) ve [hiersvr](../overview/visual-cpp-samples.md)'yi incelemek de faydalı olur.

## <a name="implement-a-drop-source"></a><a name="implement-a-drop-source"></a>Bırakma kaynağı uygulama

Uygulamanızı bir sürükle ve bırak işlemine veri sağlayacak şekilde almak için bir bırakma kaynağı uygulamalısınız. Bir bırakma kaynağının temel uygulanması nispeten basittir. İlk adım, hangi olayların bir sürükleme işlemine başlayaceğini belirlemektir. Önerilen kullanıcı arabirimi yönergeleri, bir sürükleme işleminin başlangıcını, bazı seçili verilerin içindeki bir noktada **WM_LBUTTONDOWN** bir olay gerçekleştiği sırada tanımlar. MFC OLE örnekleri [Oclient](../overview/visual-cpp-samples.md) ve [hiersvr](../overview/visual-cpp-samples.md) , bu yönergeleri izler.

Uygulamanız bir kapsayıcı ise ve seçilen veriler, türündeki bağlantılı veya katıştırılmış bir nesne ise `COleClientItem` , `DoDragDrop` üye işlevini çağırın. Aksi takdirde, bir `COleDataSource` nesne oluşturun, seçimi seçerek başlatın ve veri kaynağı nesnesinin `DoDragDrop` üye işlevini çağırın. Uygulamanız bir sunucu ise, kullanın `COleServerItem::DoDragDrop` . Standart Sürükle ve bırak davranışını özelleştirme hakkında daha fazla bilgi için [sürükle ve bırak](#customize-drag-and-drop)' ı özelleştirme bölümüne bakın.

`DoDragDrop` **DROPEFFECT_MOVE**döndürürse kaynak verileri doğrudan kaynak belgeden silin. Başka bir dönüş değeri `DoDragDrop` bırakma kaynağı üzerinde herhangi bir etkiye sahip değildir.

Daha fazla bilgi için bkz [. OLE veri nesneleri ve veri kaynakları: oluşturma ve yok etme](data-objects-and-data-sources-creation-and-destruction.md) ve [OLE veri nesneleri ve veri kaynakları: düzenleme](data-objects-and-data-sources-manipulation.md)\.

## <a name="implement-a-drop-target"></a><a name="implement-a-drop-target"></a>Bırakma hedefi uygulama

Bırakma kaynağından bir bırakma hedefi uygulamak biraz daha fazla iş kaplar, ancak yine de oldukça basittir.

### <a name="to-implement-an-ole-drop-target"></a>OLE bırakma hedefi uygulamak için

1. Henüz orada yoksa, `AfxOleInit` uygulamanızın üye işlevindeki öğesine bir çağrı ekleyin `InitInstance` . OLE kitaplıklarını başlatmak için bu çağrı gereklidir.

1. Uygulamadaki bir bırakma hedefi olmasını istediğiniz her görünüme bir üye değişkeni ekleyin. Bu üye değişkeni türünde `COleDropTarget` veya ondan türetilmiş bir sınıftan olmalıdır.

1. **WM_CREATE** iletisini işleyen Görünüm sınıfınızın işlevinizden (genellikle `OnCreate` ), yeni üye değişkeninin `Register` üye işlevini çağırın. `Revoke`, görünümlerinizin yok edileceği zaman sizin için otomatik olarak çağırılır.

1. Aşağıdaki işlevleri geçersiz kılın. Uygulamanız genelinde aynı davranışa isterseniz, görünüm sınıfınızdaki bu işlevleri geçersiz kılın. Yalıtılmış durumlarda davranışı değiştirmek veya Windows dışı bırakma işlemini etkinleştirmek istiyorsanız `CView` , bu işlevleri `COleDropTarget` türetilmiş sınıfınıza geçersiz kılın.

   | Geçersiz kıl | İzin vermek için |
   | -------- | -------- |
   | `OnDragEnter` | Pencerede gerçekleşecek bırakma işlemleri. İmleç ilk kez pencereye girdiğinde çağırılır. |
   | `OnDragLeave` | Sürükleme işlemi belirtilen pencereyi terk ettiğinde özel davranış. |
   | `OnDragOver` | Pencerede gerçekleşecek bırakma işlemleri. İmleç pencere üzerinde sürüklendiğinde çağırılır. |
   | `OnDrop` | Belirtilen pencereye bırakılan verilerin işlenmesi. |
   | `OnScrollBy` | Hedef pencerede kaydırmanın gerekli olduğu özel davranış. |

Bkz. MAINVIEW. Bu işlevlerin birlikte nasıl çalıştığı hakkında bir örnek için MFC OLE örnek [Oclient](../overview/visual-cpp-samples.md) 'ın bir PARÇASı olan cpp dosyası.

Daha fazla bilgi için bkz [. OLE veri nesneleri ve veri kaynakları: oluşturma ve yok etme](data-objects-and-data-sources-creation-and-destruction.md) ve [OLE veri nesneleri ve veri kaynakları: düzenleme](data-objects-and-data-sources-manipulation.md)\.

## <a name="customize-drag-and-drop"></a><a name="customize-drag-and-drop"></a>Sürükle ve bırak 'ı Özelleştir

Sürükle ve bırak özelliğinin varsayılan uygulaması çoğu uygulama için yeterlidir. Ancak, bazı uygulamalar bu standart davranışı değiştirmenizi gerektirebilir. Bu bölümde, bu varsayılan değerleri değiştirmek için gereken adımlar açıklanmaktadır. Bileşik belgeleri bırakma kaynaklarını desteklemeyen uygulamalar oluşturmak için bu tekniği kullanabilirsiniz.

Standart OLE sürükle ve bırak davranışını özelleştirirken veya OLE olmayan bir uygulamanız varsa, `COleDataSource` verileri içeren bir nesne oluşturmanız gerekir. Kullanıcı bir sürükle ve bırak işlemi başlattığında, kodunuz `DoDragDrop` sürükle ve bırak işlemlerini destekleyen diğer sınıfların yerine bu nesneden işlevi çağırmalıdır.

İsteğe bağlı olarak, `COleDropSource` bırakmayı denetlemek için bir nesne oluşturabilir ve değiştirmek istediğiniz davranış türüne göre bazı işlevlerini geçersiz kılabilirsiniz. Bu bırakma kaynak nesnesi daha sonra `COleDataSource::DoDragDrop` Bu işlevlerin varsayılan davranışını değiştirmek için öğesine geçirilir. Bu farklı seçenekler, uygulamanızda sürükle ve bırak işlemlerini nasıl destekledikleri konusunda harika bir esneklik sağlar. Veri kaynakları hakkında daha fazla bilgi için bkz. [veri nesneleri ve veri kaynakları (OLE)](data-objects-and-data-sources-ole.md).

Sürükle ve bırak işlemlerini özelleştirmek için aşağıdaki işlevleri geçersiz kılabilirsiniz:

| Geçersiz kıl | Özelleştirmek için |
| -------- | ------------ |
| `OnBeginDrag` | ' İ çağırdıktan sonra sürükleme işleminin başlaması `DoDragDrop` . |
| `GiveFeedback` | Farklı bırakma sonuçları için imleç görünümü gibi görsel geri bildirimler. |
| `QueryContinueDrag` | Sürükle ve bırak işleminin sonlandırılması. Bu işlev, sürükleme işlemi sırasında değiştirici anahtar durumlarını kontrol etmenizi sağlar. |

## <a name="see-also"></a>Ayrıca bkz.

[NESNE](ole-in-mfc.md)\
[OLE veri nesneleri ve veri kaynakları](data-objects-and-data-sources-ole.md)\
[OLE veri nesneleri ve veri kaynakları: oluşturma ve yok etme](data-objects-and-data-sources-creation-and-destruction.md)\
[OLE veri nesneleri ve veri kaynakları: düzenleme](data-objects-and-data-sources-manipulation.md)\
[Colet Clientıtem::D oDragDrop](reference/coleclientitem-class.md#dodragdrop)\
[Cotadatasource sınıfı](reference/coledatasource-class.md)\
[Cotadatasource::D oDragDrop](reference/coledatasource-class.md#dodragdrop)\
[COleDropSource sınıfı](reference/coledropsource-class.md)\
[COleDropTarget sınıfı](reference/coledroptarget-class.md)\
[CView:: OnDragLeave](reference/cview-class.md#ondragleave)
