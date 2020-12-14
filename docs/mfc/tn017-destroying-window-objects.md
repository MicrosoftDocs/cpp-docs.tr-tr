---
description: 'Şu konuda daha fazla bilgi edinin: TN017: pencere nesnelerini yok etme'
title: 'TN017: Pencere Nesnelerini Yok Etme'
ms.date: 11/04/2016
f1_keywords:
- vc.objects
helpviewer_keywords:
- destroying windows
- TN017
- PostNcDestroy method [MFC]
ms.assetid: 5bf208a5-5683-439b-92a1-547c5ded26cd
ms.openlocfilehash: 86ce1255055db98a247ac8997aa7d146eb135583
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215917"
---
# <a name="tn017-destroying-window-objects"></a>TN017: Pencere Nesnelerini Yok Etme

Bu notta [CWnd::P ostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy) yönteminin kullanımı açıklanmaktadır. Özelleştirilmiş türetilmiş nesneleri ayırmayı yapmak istiyorsanız bu yöntemi kullanın `CWnd` . Bu notta Ayrıca, işleç yerine bir C++ Windows nesnesini yok etmek için [CWnd::D estroyWindow](../mfc/reference/cwnd-class.md#destroywindow) kullanmanız gerektiğini de açıklanmaktadır **`delete`** .

Bu konudaki yönergeleri izlerseniz, birkaç temizleme sorununa sahip olursunuz. Bu sorunlar, C++ belleği silme/serbest bırakma, s gibi ücretsiz sistem kaynakları alma `HWND` veya nesneleri çok fazla kez boşaltma gibi sorunlardan kaynaklanabilir.

## <a name="the-problem"></a>Sorun

Her Windows nesnesi (öğesinden türetilmiş bir sınıfın nesnesi `CWnd` ) hem C++ nesnesini hem de ' i temsil eder `HWND` . C++ nesneleri uygulamanın yığınında ayrılır ve `HWND` s, pencere yöneticisi tarafından sistem kaynaklarına ayrılır. Bir pencere nesnesini yok etmek için çeşitli yollar olduğundan, sistem kaynağını veya bellek sızıntılarını önleyen bir kurallar kümesi sağlamamız gerekir. Bu kuralların aynı zamanda nesnelerin ve Windows işleyicilerinin birden çok kez yok edilmesi de önlenir.

## <a name="destroying-windows"></a>Windows yok etme

Aşağıda, bir Windows nesnesini ortadan kaldırma için izin verilen iki yol verilmiştir:

- `CWnd::DestroyWindow`Veya Windows API 'si çağrılıyor `DestroyWindow` .

- İşleciyle açıkça silme **`delete`** .

İlk durumda en sık kullanılan bir durumdur. Kodunuz doğrudan çağrımıyorsa bile bu durum geçerlidir `DestroyWindow` . Kullanıcı bir çerçeve penceresini doğrudan kapattığında, bu eylem WM_CLOSE iletisini oluşturur ve bu iletiye yönelik varsayılan yanıt `DestroyWindow.` bir üst pencere yok edildiğinde, Windows 'un `DestroyWindow` tüm alt öğeleri için çağrı yapılır.

İkinci durumda, **`delete`** Windows nesnelerinde işlecinin kullanılması nadir olmalıdır. Aşağıda, kullanmanın **`delete`** doğru seçim olduğu bazı durumlar verilmiştir.

## <a name="auto-cleanup-with-cwndpostncdestroy"></a>CWnd ile otomatik temizleme::P ostNcDestroy

Sistem bir Windows penceresini yok eder, pencereye gönderilen son Windows iletisi WM_NCDESTROY. `CWnd`Bu ileti için varsayılan Işleyici [CWnd:: OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy)' dır. `OnNcDestroy` , öğesini `HWND` C++ nesnesinden ayıracaktır ve sanal işlevi çağırır `PostNcDestroy` . Bazı sınıflar, C++ nesnesini silmek için bu işlevi geçersiz kılar.

Varsayılan uygulama `CWnd::PostNcDestroy` , yığın çerçevesine ayrılan veya diğer nesnelere eklenen pencere nesneleri için uygun hiçbir şey yapmaz. Bu, yığın üzerinde başka herhangi bir nesne olmadan ayrılacak şekilde tasarlanan pencere nesneleri için uygun değildir. Diğer bir deyişle, diğer C++ nesnelerine gömülü olmayan pencere nesneleri için uygun değildir.

Yığın üzerinde tek başına ayrılacak şekilde tasarlanan sınıflar, `PostNcDestroy` **bunu silme** işlemini gerçekleştirmek için yöntemini geçersiz kılar. Bu ifade, C++ nesnesiyle ilişkili tüm belleği boşaltacaktır. Varsayılan `CWnd` yıkıcı, `DestroyWindow` *m_hWnd* null değilse çağırır, ancak Temizleme aşamasında tanıtıcı ayrılamadığından ve null olacağı için bu, sonsuz özyineleme yapmaz.

> [!NOTE]
> Sistem genellikle `CWnd::PostNcDestroy` Windows WM_NCDESTROY iletisini tamamladıktan sonra çağırır ve `HWND` ve C++ pencere nesnesi artık bağlı değildir. Sistem Ayrıca, `CWnd::PostNcDestroy` hata oluşursa çoğu [CWnd:: Create](../mfc/reference/cwnd-class.md#create) çağrıları uygulamasını da çağırır. Otomatik temizleme kuralları bu konunun ilerleyen kısımlarında açıklanmıştır.

## <a name="auto-cleanup-classes"></a>Sınıfları otomatik temizleme

Aşağıdaki sınıflar otomatik temizleme için tasarlanmamıştır. Bunlar genellikle diğer C++ nesnelerine veya yığına katıştırılır:

- Tüm standart Windows denetimleri ( `CStatic` , `CEdit` , vb `CListBox` .).

- Doğrudan ' den türetilmiş tüm alt pencereler `CWnd` (örneğin, özel denetimler).

- Splitter pencereleri ( `CSplitterWnd` ).

- Varsayılan denetim çubukları (sınıfından türetilen sınıflar `CControlBar` , denetim çubuğu nesneleri için otomatik silme özelliğinin etkinleştirilmesi için bkz. [Teknik Not31](../mfc/tn031-control-bars.md) ).

- İletişim kutuları ( `CDialog` ) yığın çerçevesindeki kalıcı iletişim kutuları için tasarlandı.

- Dışındaki tüm standart iletişim kutuları `CFindReplaceDialog` .

- ClassWizard tarafından oluşturulan varsayılan iletişim kutuları.

Aşağıdaki sınıflar otomatik temizleme için tasarlanmıştır. Bunlar genellikle yığında kendilerine ayrılır:

- Ana çerçeve pencereleri (doğrudan veya dolaylı olarak öğesinden türetilmiş `CFrameWnd` ).

- Pencereleri görüntüleme (doğrudan veya dolaylı olarak türetilmiş `CView` ).

Bu kuralları bölmek istiyorsanız, `PostNcDestroy` türetilmiş sınıfınıza yöntemi geçersiz kılmanız gerekir. Sınıfınıza otomatik temizlik eklemek için temel sınıfınızı çağırın ve ardından bunu **silin**. Sınıfınızdan otomatik temizlemeyi kaldırmak için doğrudan `CWnd::PostNcDestroy` `PostNcDestroy` temel sınıfınızın yöntemi yerine doğrudan çağırın.

Otomatik Temizleme davranışının en yaygın kullanımı, yığın üzerinde ayrılabilen kalıcı olmayan bir iletişim kutusu oluşturmaktır.

## <a name="when-to-call-delete"></a>Silme ne zaman çağrılacağını

`DestroyWindow`Bir Windows nesnesini, C++ yöntemini ya da genel API 'yi yok etmek için çağırmanız önerilir `DestroyWindow` .

`DestroyWindow`MDI alt penceresini yok etmek için genel API 'yi çağırmayın. Bunun yerine sanal yöntemi kullanmanız gerekir `CWnd::DestroyWindow` .

Otomatik temizleme gerçekleştirmeyen C++ pencere nesneleri için, **`delete`** `DestroyWindow` `CWnd::~CWnd` VTBL, doğru türetilmiş sınıfa işaret etmez, yıkıcıya çağrı yapmayı denediğinizde bir bellek sızıntısına neden olabilir. Bu durum, sistemin çağırmak için uygun yok etme yöntemini bulamadığı için oluşur. `DestroyWindow`Yerine kullanmak **`delete`** Bu sorunları önler. Bu, hafif bir hata olabileceğinden hata ayıklama modunda derleme, risk altında olduğunda aşağıdaki uyarıyı oluşturur.

```
Warning: calling DestroyWindow in CWnd::~CWnd
    OnDestroy or PostNcDestroy in derived class will not be called
```

Otomatik Temizleme işlemi gerçekleştiren C++ Windows nesneleri söz konusu olduğunda, öğesini çağırmanız gerekir `DestroyWindow` . **`delete`** İşlecini doğrudan kullanırsanız, MFC tanılama belleği ayırıcısı, belleği iki kez boşaltırken size bildirir. İki oluşum ise ilk açık çağrılarınız ve ' nin otomatik temizleme uygulamasında **bunu silmeye** yönelik dolaylı çağrılardır `PostNcDestroy` .

`DestroyWindow`Otomatik Temizleme olmayan bir nesneyi çağırdıktan sonra, C++ nesnesi hala etrafında olacaktır, ancak *m_hWnd* null olur. `DestroyWindow`Otomatik Temizleme nesnesine çağrıldıktan sonra, c++ nesnesi, ' nin otomatik temizleme uygulamasındaki c++ delete işleci tarafından boşaltılacak şekilde silinir `PostNcDestroy` .

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
