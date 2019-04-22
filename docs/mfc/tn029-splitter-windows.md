---
title: 'TN029: Bölümlendirici Windows'
ms.date: 11/04/2016
f1_keywords:
- vc.windows.splitter
helpviewer_keywords:
- TN029
- splitter windows [MFC], about splitter windows
ms.assetid: 2c57ce99-2a3c-4eff-9cea-baccb13af075
ms.openlocfilehash: 6c2f619d9cd619ca598c66ca657faa1b9dccaaa2
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58781737"
---
# <a name="tn029-splitter-windows"></a>TN029: Bölümlendirici Windows

Bu Not MFC açıklar [CSplitterWnd sınıfı](../mfc/reference/csplitterwnd-class.md), pencere ayırır ve diğer bölmesinde pencerelerin yeniden boyutlandırmasının yönetir sağlar.

## <a name="splitter-styles"></a>Bölümlendirici stilleri

A `CSplitterWnd` windows bölme iki farklı stillerini destekler.

Oluşturulduğunda "içinde statik ayırıcılar," bölmeleri ayırıcı penceresi oluşturur. Hiçbir zaman bölmeleri sayısını ve sırasını değiştirin. Ayırıcı çubukları farklı bölmeler yeniden boyutlandırmak için kullanılır. Bu stil, farklı bir görünüm sınıfı her bir bölmede görüntülemek için kullanabilirsiniz. Visual C++ grafik Düzenleyicisi'ni ve Windows Dosya Yöneticisi bu bölme stili kullanan programlar örnekleridir. Ayırıcı penceresi bu stilini Bölümlendirici kutuları kullanmaz.

"İçinde dinamik ayırıcılar," ek bölmeleri oluşturulur ve kullanıcı gruplama ve kaldırma bölmelerini yeni görünüm olarak yok. Bu bölme, tek bir görünümle başlar ve bölme başlatan kullanıcının Bölümlendirici kutularını sağlar. Bir yönde Bölünmüş Görünüm zaman ayırıcı penceresi dinamik olarak yeni bir görünüm nesnesi oluşturur. Bu yeni görünüm nesnesi yeni bölmesini temsil eder. Klavye arabirimini kullanarak iki yönde bölünmüş görünüm ise, üç yeni görünüm nesneler için üç yeni bölme ayırıcı penceresi oluşturur. Bölme etkin durumdayken Windows Bölümlendirici kutu bölmeler arasında bir ayırıcı çubuk olarak görüntüler. Windows kullanıcı bölme kaldırır, ancak özgün görünümü kalır ayırıcı penceresi kadar yok edildiğinde ek görünüm nesnelerini yok eder. Dinamik Bölümlendirici stili kullanan uygulamaların Microsoft Excel ve Microsoft Word örnektir.

Ayırıcı penceresi ya da türünü oluşturduğunuzda, bölümlendirici yönetecek satır ve sütun sayısı belirtmelisiniz. Statik Bölümlendirici tüm satırları ve sütunları doldurmak için bölmeleri oluşturacaksınız. Dinamik Bölümlendirici yalnızca ilk bölmesinde oluşturacak, `CSplitterWnd` oluşturulur.

Statik ayırıcılar için belirttiğiniz bölmeleri sayısı 16 sütunlara göre 16 satırdır. Önerilen yapılandırmalar şunlardır:

- 1 satır x 2 sütunları: genellikle ile benzer bölmeleri

- 2 satır x 1 sütun: genellikle ile benzer bölmeleri

- 2 satır x 2 sütunları: genellikle ile benzer bölmeleri

Dinamik ayırıcılar için belirttiğiniz bölmeleri sayısı 2 sütun 2 satırdır. Önerilen yapılandırmalar şunlardır:

- 1 satır x 2 sütunları: sütunlu veri

- 2 satır x 1 sütun: metinsel veya diğer veriler için

- 2 satır x 2 sütunları: kılavuz veya tablo için veri odaklı

## <a name="splitter-examples"></a>Bölümlendirici örnekleri

MFC örnek programların birçoğu Bölümlendirici pencereler doğrudan veya dolaylı olarak kullanın. MFC genel örnek [VIEWEX](../overview/visual-cpp-samples.md) statik ayırıcılar, içinde bir ayırıcı bir ayırıcı alma dahil olmak üzere çeşitli kullanımlarını gösterir.

ClassWizard, yeni bir ayırıcı penceresi içeren birden çok belge arabirimi (MDI) alt çerçeve penceresi sınıfı oluşturmak için de kullanabilirsiniz. Bölümlendirici pencereler hakkında daha fazla bilgi için bkz. [birden çok belge türü, görünümler ve çerçeve Windows](../mfc/multiple-document-types-views-and-frame-windows.md).

## <a name="terminology-used-by-implementation"></a>Uygulama tarafından kullanılan terimler

Bölümlendirici pencereler için belirli koşullar listesi şu şekildedir:

`CSplitterWnd`: Denetimleri bölmesinde bölme ve bir satır veya sütun tüm bölmeler arasında paylaşılan bir kaydırma çubukları sağlar bir pencere. Satırları ve sütunları ile sıfır tabanlı numaralarını belirtme (satır ilk bölmesidir = 0 ve sütun = 0).

Bölmesi: Bir uygulamaya özgü penceresi, bir `CSplitterWnd` yönetir. Bir bölme genellikle türetilen bir nesnedir [CView sınıfı](../mfc/reference/cview-class.md), ancak herhangi biri [CWnd](../mfc/reference/cwnd-class.md) uygun alt penceresi kimliğe sahip nesne

Kullanılacak bir `CWnd`-türetilmiş nesne, nesnenin RUNTIME_CLASS geçirmek `CreateView` işlevini kullandıysanız, olduğu gibi bir `CView`-türetilmiş sınıf. Çalışma zamanında dinamik oluşturma framework kullandığından sınıfınıza DECLARE_DYNCREATE ve IMPLEMENT_DYNCREATE kullanmanız gerekir. Çok fazla kod olsa `CSplitterWnd` özgü olan `CView` sınıfı [CObject::IsKindOf](../mfc/reference/cobject-class.md#iskindof) bu eylemlerin gerçekleştirilmesi önce her zaman kullanılır.

Ayırıcıyı: Satırları ve sütunları bölme yerleştirilen bir denetimdir. Satır boyutunu veya sütunları bölme ayarlamak için kullanılabilir.

Bölümlendirici kutusu: Bir denetimi dinamik olarak `CSplitterWnd` yeni satırları veya sütunları bölme oluşturmak için kullanabilirsiniz. Dikey kaydırma çubuklarının veya yatay kaydırma çubuklarını solundaki üstünde bulunur.

Bölümlendirici kesişimi: Dikey bölme çubuğunu ve yatay bölme çubuğunu kesişimidir. Aynı anda bir satır ve sütunları bölme boyutunu ayarlamak için sürükleyebilirsiniz.

## <a name="shared-scroll-bars"></a>Paylaşılan kaydırma çubukları

`CSplitterWnd` Sınıfı, paylaşılan bir kaydırma çubukları de destekler. Alt öğeleri bu kaydırma çubuğu denetimleri olan `CSplitterWnd` ve farklı bölmeler ile ayırıcı paylaşılır.

Örneğin, 1 satır x 2 sütun penceresinde WS_VSCROLL oluştururken belirtebilirsiniz `CSplitterWnd`. Windows, iki bölme arasındaki paylaşılan özel kaydırma çubuğu denetimi oluşturur.

```
[      ][      ][^]
[pane00][pane01][|]
[      ][      ][v]
```

Kullanıcı kaydırma çubuğunu hareket ettirdiğinde WM_VSCROLL iletileri için her iki görünümde gönderilir. İki görünüm, kaydırma çubuğu konumu ayarladığında, paylaşılan bir kaydırma çubuğunun ayarlanır.

Paylaşılan bir kaydırma çubukları ile benzer bir görünüm nesneleri faydalı olduğunu unutmayın. Farklı türde bir ayırıcı görünümlerini karıştırmak, kaydırma konumlarına koordine etmek için özel kod yazmak olabilir. Tüm `CView`-kullanan sınıf türetilmiş `CWnd` kaydırma çubuğu varsa, API'ler paylaşılan bir kaydırma çubuğuna temsilci. `CScrollView` Uygulamasıdır örneği bir `CView` destekleyen sınıfı paylaşılan kaydırma çubukları. Türetilmiş değil sınıfları `CView`, Denetim olmayan kaydırma çubuklarını kullanan sınıf ya da standart Windows uygulamaları kullanan sınıflar (örneğin, `CEditView`) paylaşılan bir kaydırma çubuğu özelliğiyle çalışmaz `CSplitterWnd`.

## <a name="minimum-sizes"></a>En düşük boyutları

Her satır için en küçük satır yüksekliği yoktur ve her sütun için en az sütun genişliğini yoktur. Bu en az bir bölme tam ayrıntılı olarak gösterilecek küçük olduğunu garanti eder.

Statik Bölümlendirici pencere için ilk en küçük satır yüksekliğini ve sütun genişliği 0'dır. Dinamik Bölümlendirici pencere için ilk en küçük satır yüksekliğini ve sütun genişliğini ayarlanır *sizeMin* parametresinin `CSplitterWnd::Create` işlevi.

Bu en düşük boyutları kullanarak değiştirebileceğiniz [CSplitterWnd::SetRowInfo](../mfc/reference/csplitterwnd-class.md#setrowinfo) ve [CSplitterWnd::SetColumnInfo](../mfc/reference/csplitterwnd-class.md#setcolumninfo) işlevleri.

## <a name="actual-vs-ideal-sizes"></a>Gerçek vs. İdeal boyutu

Bölümlendirici pencere bölmelerinde düzenini bunları içeren çerçeveyi boyutuna bağlıdır. İçeren çerçevenin bir kullanıcı yeniden boyutlandırdığında `CSplitterWnd` bölmeleri bunların yanı sıra mümkün olan en uygun olacak şekilde yeniden boyutlandırır ve yeniden konumlandırır.

Kullanıcı, el ile satır yüksekliğini ve sütun genişliği boyutları ayarlayabilirsiniz veya program ideal boyutu kullanarak ayarlayabilirsiniz `CSplitterWnd` sınıfı. Gerçek boyut, küçük veya bu ideal daha büyük olabilir. İdeal boyutu görüntülemek için yeterli alan yoksa veya sağında veya altında ayırıcı penceresi üzerinde çok fazla boş alan yoksa Windows gerçek boyutu uyum sağlar.

## <a name="custom-controls"></a>Özel denetimler

Özelleştirilmiş davranışı ve özelleştirilmiş bir arabirim sağlamak için birçok işlev geçersiz kılabilirsiniz. Ayırıcı penceresi çeşitli grafik bileşenleri için alternatif tanımayı sağlamak için bu ilk kümesi geçersiz kılabilirsiniz.

- `virtual void OnDrawSpltter(CDC* pDC, ESplitType nType, const CRect& rect);`

- `virtual void OnInvertTracker(const CRect& rect);`

Paylaşılan bir kaydırma çubuğu denetimi oluşturmak için bu işlevi çağırın. Kaydırma çubuğunun yanındaki ek denetimler oluşturmak için geçersiz kılabilirsiniz.

- `virtual BOOL CreateScrollBarCtrl(DWORD dwStyle, UINT nID);`

Bu işlevler, dinamik Bölümlendirici penceresinin mantığını uygular. Daha gelişmiş Bölümlendirici mantığını sağlamak için bunları geçersiz kılabilirsiniz.

- `virtual void DeleteView(int row, int col);`

- `virtual BOOL SplitRow(int cyBefore);`

- `virtual BOOL SplitColumn(int cxBefore);`

- `virtual void DeleteRow(int rowDelete);`

- `virtual void DeleteColumn(int colDelete);`

## <a name="cview-functionality"></a>CView işlevi

`CView` Sınıfı temsilci olarak üst düzey aşağıdaki komutları kullanır `CSplitterWnd` uygulaması. Bu komutları sanal olduğundan standart `CView` uygulama değil tüm gerekli `CSplitterWnd` uygulama bağlı. Kullanan uygulamalar için `CView` ama `CSplitterWnd`, `CSplitterWnd` uygulaması bağlı değil uygulama ile.

- `virtual BOOL CanActivateNext(BOOL bPrev = FALSE);`

   Id_next_pane veya ıd_prev_pane şu anda mümkün olup olmadığını denetler.

- `virtual void ActivateNext(BOOL bPrev = FALSE);`

   "Sonraki Bölme" veya "Önceki Bölme" komutu yürütür.

- `virtual BOOL DoKeyboardSplit();`

   Komutu, genellikle "Window Split" klavye yürütür.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
