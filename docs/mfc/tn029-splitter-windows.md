---
title: "TN029: Bölünmüş Pencereler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.windows.splitter
dev_langs:
- C++
helpviewer_keywords:
- TN029
- splitter windows [MFC], about splitter windows
ms.assetid: 2c57ce99-2a3c-4eff-9cea-baccb13af075
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 95b7db2678c03b0508a1507567f8bedcf243cd4a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="tn029-splitter-windows"></a>TN029: Bölünmüş Pencereler
MFC bu not açıklar [CSplitterWnd sınıfı](../mfc/reference/csplitterwnd-class.md), pencere ayırır ve diğer bölmesinde Windows'un yeniden boyutlandırma yönetir sağlar.  
  
## <a name="splitter-styles"></a>Bölümlendirici stilleri  
 A `CSplitterWnd` windows bölme iki farklı stillerini destekler.  
  
 Oluşturulduğunda "statik ayırıcılar," Bölümlendirici pencere bölmeleri oluşturur. Hiçbir zaman sırasını ve bölmeleri sayısını değiştirin. Ayırıcı çubukları farklı bölmeleri yeniden boyutlandırmak için kullanılır. Farklı bir görünüm sınıfı her bölmesinde görüntülemek için bu stili kullanabilirsiniz. Visual C++ grafik Düzenleyicisi'ni ve Windows Dosya Yöneticisi'ni bu Bölümlendirici stili kullanan programlar örnektir. Bölümlendirici pencere bu stilini Bölümlendirici kutuları kullanmaz.  
  
 "İçinde dinamik ayırıcılar," ek bölmeleri oluşturulur ve kullanıcı bölmelerini ve kaydını bölmelerini yeni görünümler yok. Bu ayırıcı tek bir görünümü ile başlar ve bölme başlatan kullanıcının Bölümlendirici kutularının sağlar. Görünüm tek yönlü böldüğünüzde Bölümlendirici pencere dinamik olarak yeni bir görünüm nesnesi oluşturur. Bu yeni görünüm nesnesi yeni bölmesi temsil eder. Klavye arabirimini kullanarak iki yönde de görünümü bölünmüş ise, bölümlendirici pencere üç yeni bölmeleri için üç yeni görünüm nesneleri oluşturur. Bölünmüş etkinken Windows Bölümlendirici kutusunu bölmeleri arasına bir ayırıcı çubuk olarak görüntüler. Windows kullanıcı bölme kaldırır, ancak özgün görünümü kalır Bölümlendirici pencere kadar bozulur ek görünüm nesneleri yok eder. Microsoft Excel ve Microsoft Word Dinamik Bölümlendirici stili kullanan uygulamalar örnekleridir.  
  
 Bölümlendirici pencere her iki tür oluşturduğunuzda, en fazla satır ve sütun sayısı, bölümlendirici yönetecek belirtmeniz gerekir. Statik Bölümlendirici tüm satırları ve sütunları doldurmak için bölmeleri oluşturur. Dinamik Bölümlendirici yalnızca ilk bölmesinde oluşturacak zaman `CSplitterWnd` oluşturulur.  
  
 En fazla bölmeleri için statik ayırıcılar belirtebilirsiniz 16 sütundan 16 satır sayısıdır. Önerilen yapılandırmaları şunlardır:  
  
-   1 satır x 2 sütunları: genellikle farklı bölmeleri ile  
  
-   2 satır x 1 sütun: genellikle farklı bölmeleri ile  
  
-   2 satır x 2 sütunlar: genellikle ile benzer bölmeleri  
  
 En fazla dinamik ayırıcılar için belirttiğiniz bölmeleri 2 sütun 2 satır sayısıdır. Önerilen yapılandırmaları şunlardır:  
  
-   1 satır x 2 sütunları: sütunlu veriler için  
  
-   2 satır x 1 sütun: metinsel veya diğer veriler için  
  
-   2 satır x 2 sütunlar: ızgara veya tablo için veri odaklı  
  
## <a name="splitter-examples"></a>Bölümlendirici örnekleri  
 MFC örnek programlar çoğunu Bölümlendirici pencereler doğrudan veya dolaylı olarak kullanın. MFC genel örnek [VIEWEX](../visual-cpp-samples.md) statik ayırıcılar bir ayırıcı bir ayırıcı yerleştirmek de dahil olmak üzere, birkaç kullanımını gösterir.  
  
 ClassWizard, yeni bir Bölümlendirici pencere içeren birden çok belge arabirimi (MDI) alt çerçeve pencere sınıfı oluşturmak için de kullanabilirsiniz. Bölümlendirici pencereler hakkında daha fazla bilgi için bkz: [birden çok belge türü, görünümler ve çerçeve pencereleri](../mfc/multiple-document-types-views-and-frame-windows.md).  
  
## <a name="terminology-used-by-implementation"></a>Uygulama tarafından kullanılan terminolojisi  
 Bölümlendirici pencereler belirli terimleri listesi aşağıdadır:  
  
 `CSplitterWnd`:  
 Bölmesinde bölme denetimi ve bir satır veya sütun tüm bölmeleri arasında paylaşılan kaydırma çubukları sağlayan bir pencere. Sıfır tabanlı numaralarıyla satırları ve sütunları belirtin (satır ilk bölmesidir = 0 ve sütun = 0).  
  
 Bölmesi:  
 Bir uygulamaya özgü penceresi, bir `CSplitterWnd` yönetir. Bir bölme genellikle türetilmiş bir nesnedir [CView sınıfı](../mfc/reference/cview-class.md), ancak herhangi [CWnd](../mfc/reference/cwnd-class.md) uygun alt pencere kimliğine sahip nesne  
  
 Kullanılacak bir `CWnd`-türetilen nesne, geçirmek `RUNTIME_CLASS` nesnenin `CreateView` işlev, kullanıyormuş gibi bir `CView`-türetilmiş sınıf. Sınıfınızda kullanmalısınız `DECLARE_DYNCREATE` ve `IMPLEMENT_DYNCREATE` framework çalışma zamanında dinamik oluşturma kullandığından. Kod içinde çok olsa `CSplitterWnd` özgü olan `CView` sınıfı, [CObject::IsKindOf](../mfc/reference/cobject-class.md#iskindof) bu eylemlerin gerçekleştirildiğinden önce her zaman kullanılır.  
  
 Bölümlendirici çubuğu:  
 Satırları ve sütunları bölmeleri, arasında yerleştirilmiş denetim. Satır boyutları veya bölmeleri sütunlarının ayarlamak için kullanılabilir.  
  
 Bölümlendirici kutusu:  
 Dinamik bir denetimde `CSplitterWnd` yeni satırlar veya bölmeleri sütunlarının oluşturmak için kullanabilirsiniz. Yatay kaydırma çubuklarını solundaki dikey kaydırma çubukları ve üstünde bulunur.  
  
 Bölümlendirici kesişimi:  
 Yatay bölme çubuğunu ve Yatay bölümlendirici çubuğu kesişimi. Bir satır ve sütun bölmeleri, boyutunu aynı anda ayarlamak için sürükleyebilirsiniz.  
  
## <a name="shared-scroll-bars"></a>Paylaşılan kaydırma çubukları  
 `CSplitterWnd` Sınıfı, paylaşılan kaydırma çubukları de destekler. Bu kaydırma çubuğu denetimleri alt öğeleri olan `CSplitterWnd` ve farklı bölmeleri ile Bölümlendirici paylaşılır.  
  
 Örneğin, bir 1 satır x 2 sütun penceresinde, WS_VSCROLL oluştururken belirtebilirsiniz `CSplitterWnd`. Windows iki bölme arasında paylaşılan bir özel kaydırma çubuğu denetimi oluşturur.  
  
```  
[      ][      ][^]  
[pane00][pane01][|]  
[      ][      ][v]  
```  
  
 Kullanıcı kaydırma çubuğu taşıdığında `WM_VSCROLL` iletileri için her iki görünümde gönderilir. Kaydırma çubuğu konumu ya da Görünüm ayarlar, paylaşılan kaydırma çubuğu ayarlanır.  
  
 Paylaşılan kaydırma çubukları benzer görünüm nesneleriyle en yararlı olduğunu unutmayın. Farklı türde bir ayırıcı görünümlerini karışımı, kaydırma konumlarına koordine etmek için özel kod yazmanıza izin olabilir. Tüm `CView`-kullanan sınıfı türetilmiş `CWnd` kaydırma çubuğu varsa, API paylaşılan kaydırma çubuğuna temsilci. `CScrollView` Uygulamasıdır bir örneği bir `CView` destekleyen sınıfı paylaşılan kaydırma çubukları. Öğesinden türetilmemiş sınıfları `CView`, Denetim olmayan kaydırma çubukları kullanan sınıfları veya standart Windows uygulamalarını kullanın sınıfları (örneğin, `CEditView`) paylaşılan kaydırma çubuğu özelliğiyle çalışmaz `CSplitterWnd`.  
  
## <a name="minimum-sizes"></a>Minimum boyutları  
 Her satır için en az satır yüksekliğini yoktur ve her sütun için en az bir sütun genişliği yoktur. Bu en az bir bölme tam ayrıntılı olarak gösterilmesi için çok küçük değil güvence altına alır.  
  
 Statik Bölümlendirici pencere için ilk en az satır yüksekliğini ve sütun genişliği 0'dır. Dinamik Bölümlendirici pencere için ilk en az satır yüksekliğini ve sütun genişliği ayarlanır `sizeMin` parametresinin `CSplitterWnd::Create` işlevi.  
  
 Bu en az boyutları kullanarak değiştirebilirsiniz [CSplitterWnd::SetRowInfo](../mfc/reference/csplitterwnd-class.md#setrowinfo) ve [CSplitterWnd::SetColumnInfo](../mfc/reference/csplitterwnd-class.md#setcolumninfo) işlevleri.  
  
## <a name="actual-vs-ideal-sizes"></a>Gerçek vs. İdeal boyutu  
 Bölümlendirici pencere bölmelerinde düzenini onları içeren çerçeve boyutuna bağlıdır. Bir kullanıcı içeren çerçeve yeniden boyutlandırır zaman `CSplitterWnd` yeniden konumlandırır ve bunların yanı sıra olası uyacak şekilde, bölmeleri yeniden boyutlandırır.  
  
 Kullanıcı yüksekliğini ve sütun genişliği boyutları satır el ile ayarlayabilirsiniz veya program ideal boyutu kullanarak ayarlayabilirsiniz `CSplitterWnd` sınıfı. Gerçek boyut, daha küçük veya ideal daha büyük olabilir. Windows gerçek boyutu ideal boyutu görüntülemek için yeterli alan yoksa veya sağa ya da Bölümlendirici penceresinin alt kısmındaki üzerinde çok fazla boş alanı ise ayarlanır.  
  
## <a name="custom-controls"></a>Özel denetimler  
 Özelleştirilmiş davranışı ve özelleştirilmiş bir arabirim sağlamak için birçok işlevini geçersiz kılabilirsiniz. Bölümlendirici pencere çeşitli grafik bileşenleri için alternatif görüntülerin sağlamak için bu ilk kümesi geçersiz kılabilirsiniz.  
  
- `virtual void OnDrawSpltter(CDC* pDC, ESplitType nType, const CRect& rect);`  
  
- `virtual void OnInvertTracker(const CRect& rect);`  
  
 Paylaşılan kaydırma çubuğu denetimi oluşturmak için bu işlevini çağırın. Kaydırma çubuğu yanındaki ek denetimleri oluşturmak için geçersiz kılabilirsiniz.  
  
- `virtual BOOL CreateScrollBarCtrl(DWORD dwStyle, UINT nID);`  
  
 Bu işlevler dinamik Bölümlendirici pencere mantığını uygular. Daha gelişmiş Bölümlendirici mantığın geçersiz kılabilirsiniz.  
  
- `virtual void DeleteView(int row, int col);`  
  
- `virtual BOOL SplitRow(int cyBefore);`  
  
- `virtual BOOL SplitColumn(int cxBefore);`  
  
- `virtual void DeleteRow(int rowDelete);`  
  
- `virtual void DeleteColumn(int colDelete);`  
  
## <a name="cview-functionality"></a>CView işlevi  
 `CView` Sınıfı için temsilci seçmek için aşağıdaki üst düzey komutlar kullanır `CSplitterWnd` uygulaması. Bu komutlar sanal, çünkü standart `CView` uygulama değil tüm gerektiren `CSplitterWnd` uygulama bağlı. Kullanan uygulamalar için `CView` ama `CSplitterWnd`, `CSplitterWnd` uygulaması bağlı değil uygulama ile.  
  
 `virtual BOOL CanActivateNext(BOOL bPrev = FALSE);`  
 Id_next_pane veya ıd_prev_pane şu anda mümkün olup olmadığını denetler.  
  
 `virtual void ActivateNext(BOOL bPrev = FALSE);`  
 "Sonraki Bölme" veya "Önceki Bölme" komutunu çalıştırır.  
  
 `virtual BOOL DoKeyboardSplit();`  
 Komut, "Pencere bölünmüş" genellikle bölme klavye yürütür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

