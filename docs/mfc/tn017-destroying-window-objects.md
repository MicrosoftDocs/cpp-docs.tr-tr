---
title: 'TN017: Pencere Nesnelerini Yok Etme'
ms.date: 11/04/2016
f1_keywords:
- vc.objects
helpviewer_keywords:
- destroying windows
- TN017
- PostNcDestroy method [MFC]
ms.assetid: 5bf208a5-5683-439b-92a1-547c5ded26cd
ms.openlocfilehash: 9802669468cbbba89f23b8ac127358d1fc15ec9f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370417"
---
# <a name="tn017-destroying-window-objects"></a>TN017: Pencere Nesnelerini Yok Etme

Bu [not, CWnd kullanımını açıklar::PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy) yöntemi. Türetilmiş nesnelerin özelleştirilmiş tahsisini `CWnd`yapmak istiyorsanız bu yöntemi kullanın. Bu not, **silme** işleci yerine C++ Windows nesnesini yok etmek için neden [CWnd::DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow) kullanmanız gerektiğini de açıklar.

Bu konudaki yönergeleri izlerseniz, birkaç temizleme sorununuz olacaktır. Bu sorunlar, C++ belleği silmeyi/boşaltmayı unutma, s gibi `HWND`özgür sistem kaynaklarını unutma veya nesneleri çok fazla serbest etme gibi sorunlardan kaynaklanabilir.

## <a name="the-problem"></a>Sorun

Her windows nesnesi (türetilen bir sınıfın `CWnd`nesnesi) hem C++ nesnesini hem de . `HWND` C++ nesneleri uygulamanın yığınına ayrılır ve `HWND`s pencere yöneticisi tarafından sistem kaynaklarına ayrılır. Bir pencere nesnesini yok etmenin birkaç yolu olduğundan, sistem kaynağının veya bellek sızıntılarının önüne geçen bir dizi kural sağlamamız gerekir. Bu kurallar, nesnelerin ve Windows tutamaçlarının birden fazla kez yok olmasını da engellemelidir.

## <a name="destroying-windows"></a>Windows'u Yok Etme

Bir Windows nesnesini yok etmenin iki izin verilen yolu şunlardır:

- Arama `CWnd::DestroyWindow` veya Windows `DestroyWindow`API.

- **Silme** işleciyle açıkça silme.

İlk vaka açık ara en yaygın olanıdır. Bu durum, kodunuz doğrudan aramasa `DestroyWindow` bile geçerlidir. Kullanıcı bir çerçeve penceresini doğrudan kapattığında, bu eylem WM_CLOSE iletisini oluşturur ve `DestroyWindow.` bu iletiye varsayılan yanıt, `DestroyWindow` bir üst pencere yok edildiğinde, Windows tüm alt çocuklarını çağırır.

İkinci durumda, Windows nesneleri üzerinde **silme** işleci nin kullanımı, nadir olmalıdır. Sil'i **kullanmanın** doğru seçim olduğu bazı durumlar aşağıda veda edilebilgilidir.

## <a name="auto-cleanup-with-cwndpostncdestroy"></a>CWnd ile Otomatik Temizlik::PostNcDestroy

Sistem bir Windows penceresini yok ettiğinde, pencereye gönderilen son Windows iletisi WM_NCDESTROY. Bu `CWnd` ileti için varsayılan işleyici [CWnd::OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy)olduğunu. `OnNcDestroy`C++ `HWND` nesnesinden ayıracak ve sanal işlevi `PostNcDestroy`çağıracaktır. Bazı sınıflar C++ nesnesini silmek için bu işlevi geçersiz kılar.

Yığın çerçevesine `CWnd::PostNcDestroy` ayrılan veya diğer nesnelere katıştırılmış pencere nesneleri için uygun olan hiçbir şey yapmaz varsayılan uygulaması. Bu, başka nesneler olmadan yığına ayrılacak şekilde tasarlanmış pencere nesneleri için uygun değildir. Başka bir deyişle, diğer C++ nesnelerine katıştırılmış olmayan pencere nesneleri için uygun değildir.

Yığınüzerinde tek başına tahsis edilecek şekilde tasarlanan bu `PostNcDestroy` **sınıflar, bunu silmek**için yöntemi geçersiz kılar. Bu bildirim, C++ nesnesi ile ilişkili herhangi bir bellek serbest olacaktır. Varsayılan `CWnd` yıkıcı *m_hWnd* NULL değilse `DestroyWindow` çağırır olsa da, bu sonsuz özyinelemeye yol açmaz, çünkü işlem temizleme aşamasında kopuk ve NULL olacaktır.

> [!NOTE]
> Sistem genellikle `CWnd::PostNcDestroy` Windows WM_NCDESTROY iletisini işledikten sonra çağırır ve `HWND` C++ pencere nesnesi artık bağlı değildir. Sistem ayrıca çoğu `CWnd::PostNcDestroy` CWnd'nin uygulanmasında çağrıda [bulunacak::Hata](../mfc/reference/cwnd-class.md#create) oluşursa arama lar oluşturun. Otomatik temizleme kuralları daha sonra bu konuda açıklanmıştır.

## <a name="auto-cleanup-classes"></a>Otomatik Temizleme Sınıfları

Aşağıdaki sınıflar otomatik temizleme için tasarlanmaz. Genellikle diğer C++ nesnelerine veya yığına katıştirilirler:

- Tüm standart Windows`CStatic` `CEdit`denetimleri ( , , `CListBox`, ve benzeri).

- Doğrudan türetilen alt `CWnd` pencereler (örneğin, özel denetimler).

- Splitter pencereleri (`CSplitterWnd`).

- Varsayılan denetim çubukları (denetim çubuğu nesneleri için otomatik silmeyi etkinleştirmek için Teknik Not `CControlBar` [31'den](../mfc/tn031-control-bars.md) türetilen sınıflar).

- Yığın çerçevesi`CDialog`üzerindeki modal iletişim kutuları için tasarlanmış diyaloglar .

- Hariç tüm standart iletişim `CFindReplaceDialog`

- ClassWizard tarafından oluşturulan varsayılan iletişim kutuları.

Aşağıdaki sınıflar otomatik temizleme için tasarlanmıştır. Genellikle yığın üzerinde kendileri tarafından tahsis edilir:

- Ana çerçeve pencereleri (doğrudan `CFrameWnd`veya dolaylı olarak türetilmiştir).

- Pencereleri görüntüleyin (doğrudan `CView`veya dolaylı olarak türetilmiştir).

Bu kuralları kırmak istiyorsanız, türemiş `PostNcDestroy` sınıfınızdaki yöntemi geçersiz kılmanız gerekir. Sınıfınıza otomatik temizleme eklemek için taban sınıfınızı arayın ve sonra **bunu silin.** Sınıfınızdan otomatik temizlemeyi kaldırmak için, doğrudan `PostNcDestroy` taban sınıfınızın yöntemi yerine doğrudan arayın. `CWnd::PostNcDestroy`

Otomatik temizleme davranışını değiştirmenin en yaygın kullanımı, yığına ayrılabilecek biçimsiz bir iletişim oluşturmaktır.

## <a name="when-to-call-delete"></a>Silme Ne Zaman Çağrı

C++ yöntemi `DestroyWindow` veya genel `DestroyWindow` API gibi bir Windows nesnesini yok etmek için aramanızı öneririz.

Bir MDI `DestroyWindow` Child penceresini yok etmek için genel API'yi aramayın. Bunun yerine sanal `CWnd::DestroyWindow` yöntemi kullanmalısınız.

Otomatik temizleme yapmayan C++ Penceresi nesneleri için, **Silmek** işlecini kullanmak, VTBL `DestroyWindow` doğru `CWnd::~CWnd` türetilen sınıfı işaret etmiyorsa yıkıcıyı çağırmaya çalıştığınızda bellek sızıntısına neden olabilir. Sistem aramak için uygun yok etme yöntemini bulamıyor çünkü bu oluşur. Silme `DestroyWindow` yerine **delete** kullanmak bu sorunları önler. Bu ince bir hata olabileceğinden, hata ayıklama modunda derleme niz risk altındaysa aşağıdaki uyarıyı oluşturur.

```
Warning: calling DestroyWindow in CWnd::~CWnd
    OnDestroy or PostNcDestroy in derived class will not be called
```

Otomatik temizleme gerçekleştiren C++ Windows nesneleri söz konusu olduğunda, `DestroyWindow`. **Silme** işlecinin doğrudan kullanılması durumunda, MFC tanılama bellek ayırıcısı size belleği iki kez serbest yaptığınızı bildirir. İki olay ilk açık arama ve dolaylı çağrı otomatik temizleme uygulamasında **bu silmek** için `PostNcDestroy`.

Otomatik `DestroyWindow` temizleme olmayan bir nesneyi çağırdıktan sonra, C++ nesnesi hala etrafta olacak, ancak *m_hWnd* NULL olacaktır. Otomatik `DestroyWindow` temizleme nesnesini `PostNcDestroy`aradıktan sonra, C++ nesnesi gitmiş olacak ve otomatik temizleme uygulamasında C++ silme işleci tarafından serbest bırakılacak.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
