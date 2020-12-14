---
description: 'Daha fazla bilgi edinin: TN029: Splitter Windows'
title: 'TN029: Bölünmüş Pencereler'
ms.date: 11/04/2016
f1_keywords:
- vc.windows.splitter
helpviewer_keywords:
- TN029
- splitter windows [MFC], about splitter windows
ms.assetid: 2c57ce99-2a3c-4eff-9cea-baccb13af075
ms.openlocfilehash: e1079adf403b64aa47f5aae00aa32f7da702ddcf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215644"
---
# <a name="tn029-splitter-windows"></a>TN029: Bölünmüş Pencereler

Bu notta, pencere, diğer bölme pencerelerinin yeniden boyutlandırmasını sağlayan MFC [CSplitterWnd sınıfı](../mfc/reference/csplitterwnd-class.md)açıklanır.

## <a name="splitter-styles"></a>Ayırıcı stilleri

`CSplitterWnd`, Pencereleri bölmek için iki farklı stili destekler.

"Statik ayırıcılar" içinde, ayırıcı penceresi oluşturulduğunda bölmeleri oluşturur. Bölmelerin sırası ve sayısı hiçbir şekilde değişmez. Ayırıcı çubuklar, farklı bölmeleri yeniden boyutlandırmak için kullanılır. Bu stili, her bölmede farklı bir görünüm sınıfı görüntülemek için kullanabilirsiniz. Visual C++ grafik Düzenleyicisi ve Windows Dosya Yöneticisi, bu ayırıcı stili kullanan programların örnekleridir. Bu ayırıcı pencere stili Splitter kutularını kullanmaz.

"Dinamik bölümlendiricileri" içinde, Kullanıcı yeni görünümleri bölmeleri ve bölünmeyeceği için ek bölmeler oluşturulur ve yok edilir. Bu Bölümlendirici tek bir görünümle başlatılır ve kullanıcının bölmeyi başlatması için Bölümlendirici kutular sağlar. Görünüm bir yöne bölündüğünde ayırıcı pencere dinamik olarak yeni bir görünüm nesnesi oluşturur. Bu yeni görünüm nesnesi yeni bölmeyi temsil eder. Görünüm, klavye arabirimini kullanarak iki yönde bölündüğünde, ayırıcı penceresi üç yeni bölme için üç yeni görünüm nesnesi oluşturur. Bölünmüş etkin olsa da, pencereler bölme kutusunu bölmeler arasında bir ayırıcı çubuk olarak görüntüler. Kullanıcı bir bölmeyi kaldırdığında Windows ek görünüm nesnelerini yok eder, ancak ayırıcı pencere yok edilinceye kadar özgün görünüm kalır. Microsoft Excel ve Microsoft Word, dinamik ayırıcı stilini kullanan uygulamalara örnektir.

Herhangi bir tür ayırıcı penceresi oluşturduğunuzda, ayırıcının yöneteceği en fazla satır ve sütun sayısını belirtmeniz gerekir. Statik Bölümlendirici, tüm satırları ve sütunları dolduracak bölmeler oluşturur. Dinamik Bölümlendirici, oluşturulduğunda yalnızca ilk bölmeyi oluşturacaktır `CSplitterWnd` .

Statik bölümlendiricileri için belirtebileceğiniz en fazla bölme sayısı 16 satırdır. Önerilen konfigürasyonlar şunlardır:

- 1 satır x 2 sütun: genellikle benzer bölmelerle

- 2 satır x 1 sütun: genellikle benzer bölmeler ile

- 2 satır x 2 sütun: genellikle benzer bölmelerle

Dinamik bölümlendiricileri için belirtebileceğiniz en fazla bölme sayısı 2 satırdır. Önerilen konfigürasyonlar şunlardır:

- 1 satır x 2 sütun: sütunlu veriler için

- 2 satır x 1 sütun: metin veya diğer veriler için

- 2 satır x 2 sütun: kılavuz veya tablo odaklı veriler için

## <a name="splitter-examples"></a>Splitter örnekleri

MFC örnek programlarının birçoğu doğrudan veya dolaylı olarak Bölümlendirici pencereler kullanır. MFC genel örnek [Viewex](../overview/visual-cpp-samples.md) , bir ayırıcıyı Bölümlendirici yerleştirme dahil olmak üzere birkaç statik Bölümlendirici kullanımını gösterir.

Ayrıca, bir Splitter penceresi içeren yeni bir çoklu belge arabirimi (MDI) alt çerçeve pencere sınıfı oluşturmak için ClassWizard 'ı kullanabilirsiniz. Bölünmüş pencereler hakkında daha fazla bilgi için bkz. [birden fazla belge türü, görünüm ve çerçeve penceresi](../mfc/multiple-document-types-views-and-frame-windows.md).

## <a name="terminology-used-by-implementation"></a>Uygulama tarafından kullanılan terminoloji

Bölünmüş pencereler için özel terimlerin listesi aşağıda verilmiştir:

`CSplitterWnd`: Bir satır veya sütundaki tüm bölmeler arasında paylaşılan bölme denetimleri ve kaydırma çubukları sağlayan bir pencere. Sıfır tabanlı sayılarla satırları ve sütunları belirtirsiniz (ilk bölme satır = 0 ve sütun = 0).

Bölmesi: tarafından yönetilen uygulamaya özgü bir pencere `CSplitterWnd` . Bir bölme genellikle [CView sınıfından](../mfc/reference/cview-class.md)türetilmiş bir nesnedir, ancak uygun alt pencere kimliğine sahip herhangi bir [CWnd](../mfc/reference/cwnd-class.md) nesnesi olabilir.

Türetilmiş bir nesneyi kullanmak için `CWnd` , ' ın `CreateView` türetilmiş bir sınıfı kullanırken olduğu gibi, işlevin RUNTIME_CLASS işleve geçirin `CView` . Çerçeve, çalışma zamanında dinamik oluşturma kullandığından, sınıfınızın DECLARE_DYNCREATE ve IMPLEMENT_DYNCREATE kullanması gerekir. ' De sınıfına özgü birçok kod olsa da `CSplitterWnd` `CView` , bu eylemler gerçekleştirilmeden önce [CObject:: IsKindOf](../mfc/reference/cobject-class.md#iskindof) her zaman kullanılır.

Ayırıcı çubuğu: bölme satırları ve sütunları arasına yerleştirilmiş bir denetim. Bu işlem, bölme satırlarının veya sütunlarının boyutlarını ayarlamak için kullanılabilir.

Bölümlendirici kutusu: bir dinamik içinde, `CSplitterWnd` yeni satırlar veya bölme sütunları oluşturmak için kullanabileceğiniz bir denetim. Dikey kaydırma çubuklarının en üstünde veya yatay kaydırma çubuklarının solunda bulunur.

Ayırıcı kesişimi: Dikey bölümlendirici çubuğun ve yatay Bölümlendirici çubuğun kesişimi. Aynı anda bir satır ve bölme sütununun boyutunu ayarlamak için onu sürükleyebilirsiniz.

## <a name="shared-scroll-bars"></a>Paylaşılan kaydırma çubukları

`CSplitterWnd`Sınıfı, paylaşılan kaydırma çubuklarını da destekler. Bu kaydırma çubuğu denetimleri, öğesinin alt öğesi `CSplitterWnd` ve Bölümlendirici içindeki farklı bölmelerle paylaşılır.

Örneğin, 1 satır x 2 sütun penceresinde oluştururken WS_VSCROLL belirtebilirsiniz `CSplitterWnd` . Windows, iki bölme arasında paylaşılan özel bir kaydırma çubuğu denetimi oluşturur.

```
[      ][      ][^]
[pane00][pane01][|]
[      ][      ][v]
```

Kullanıcı kaydırma çubuğunu taşıdıkça, WM_VSCROLL iletiler her iki görünüme de gönderilir. Her iki görünüm de kaydırma çubuğu konumunu ayarlarsa, paylaşılan kaydırma çubuğu ayarlanır.

Paylaşılan kaydırma çubuklarının, benzer görünüm nesneleriyle en çok yararlı olduğunu unutmayın. Bir Bölümlendiricinin farklı türlerin görünümlerini karıştırırsanız, kaydırma konumlarını koordine etmek için özel kod yazmanız gerekebilir. `CView`Kaydırma çubuğu API 'lerini kullanan herhangi bir türetilmiş sınıf, varsa `CWnd` paylaşılan kaydırma çubuğunu temsil eder. `CScrollView`Uygulama, `CView` paylaşılan kaydırma çubuklarını destekleyen bir sınıfa bir örnektir. Öğesinden türetilmeyen sınıflar `CView` , denetim dışı kaydırma çubuklarına dayanan sınıflar veya standart Windows uygulamaları (örneğin,) kullanan sınıflar, ' `CEditView` nin paylaşılan kaydırma çubuğu özelliğiyle çalışmaz `CSplitterWnd` .

## <a name="minimum-sizes"></a>Minimum Boyutlar

Her satır için en az bir satır yüksekliği vardır ve her sütun için en az bir sütun genişliği bulunur. Bu en düşük değer, bir bölmenin tüm ayrıntılarla gösterilemeyecek kadar küçük olmasını garanti eder.

Statik Bölümlendirici penceresinde, başlangıçtaki en küçük satır yüksekliği ve sütun genişliği 0 ' dır. Dinamik Bölümlendirici penceresinde, başlangıçtaki en küçük satır yüksekliği ve sütun genişliği, işlevin *sizeMin* parametresine göre ayarlanır `CSplitterWnd::Create` .

Bu minimum boyutları [CSplitterWnd:: SetRowInfo](../mfc/reference/csplitterwnd-class.md#setrowinfo) ve [CSplitterWnd:: SetColumnInfo](../mfc/reference/csplitterwnd-class.md#setcolumninfo) işlevlerini kullanarak değiştirebilirsiniz.

## <a name="actual-vs-ideal-sizes"></a>Gerçek ve Ideal Boyutlar

Bölümlendirici penceresindeki bölmelerin yerleşimi, bunları içeren çerçevenin boyutuna bağlıdır. Bir Kullanıcı içerilen çerçeveyi yeniden boyutlandırdığında, `CSplitterWnd` bölmeleri mümkün olduğunca ve sığacak şekilde yeniden boyutlandırır.

Kullanıcı, satır yüksekliğini ve sütun genişliği boyutlarını el ile ayarlayabilir veya program, sınıfını kullanarak ideal boyutu ayarlayabilir `CSplitterWnd` . Gerçek Boyut ideal veya daha büyük olabilir. İdeal boyutu göstermek için yeterli alan yoksa veya ayırıcı pencerenin sağ veya altında çok fazla boş alan yoksa, Windows gerçek boyutu ayarlar.

## <a name="custom-controls"></a>Özel denetimler

Özelleştirilmiş davranışı ve özelleştirilmiş bir arabirimi sağlamak için birçok işlevi geçersiz kılabilirsiniz. Bu ilk kümeyi, bir bölücü penceresinin çeşitli grafik bileşenleri için alternatif canlandırın sağlamak üzere geçersiz kılabilirsiniz.

- `virtual void OnDrawSpltter(CDC* pDC, ESplitType nType, const CRect& rect);`

- `virtual void OnInvertTracker(const CRect& rect);`

Paylaşılan bir kaydırma çubuğu denetimi oluşturmak için bu işlevi çağırın. Kaydırma çubuğunun yanında ek denetimler oluşturmak için bunu geçersiz kılabilirsiniz.

- `virtual BOOL CreateScrollBarCtrl(DWORD dwStyle, UINT nID);`

Bu işlevler, dinamik ayırıcı penceresinin mantığını uygular. Daha gelişmiş ayırıcı mantığı sağlamak için bunları geçersiz kılabilirsiniz.

- `virtual void DeleteView(int row, int col);`

- `virtual BOOL SplitRow(int cyBefore);`

- `virtual BOOL SplitColumn(int cxBefore);`

- `virtual void DeleteRow(int rowDelete);`

- `virtual void DeleteColumn(int colDelete);`

## <a name="cview-functionality"></a>CView Işlevselliği

`CView`Sınıfı, uygulamaya temsilci atamak için aşağıdaki üst düzey komutları kullanır `CSplitterWnd` . Bu komutlar sanal olduğundan, standart `CView` uygulama tüm `CSplitterWnd` uygulamanın bağlanmasını gerektirmez. Ancak kullanan uygulamalar için `CView` `CSplitterWnd` `CSplitterWnd` uygulama uygulamayla bağlanmayacak.

- `virtual BOOL CanActivateNext(BOOL bPrev = FALSE);`

   ID_NEXT_PANE veya ID_PREV_PANE Şu anda mümkün olup olmadığını denetler.

- `virtual void ActivateNext(BOOL bPrev = FALSE);`

   "Sonraki bölme" veya "önceki bölme" komutunu yürütür.

- `virtual BOOL DoKeyboardSplit();`

   Klavye bölme komutunu genellikle "pencere Böl" olarak yürütür.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
