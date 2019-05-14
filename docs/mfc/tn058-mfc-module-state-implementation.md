---
title: 'TN058: MFC modül durumu uygulaması'
ms.date: 06/28/2018
helpviewer_keywords:
- thread state [MFC]
- module states [MFC], managing state data
- TN058
- MFC, managing state data
- module states [MFC], switching
- DLLs [MFC], module states
- process state [MFC]
ms.assetid: 72f5b36f-b3da-4009-a144-24258dcd2b2f
ms.openlocfilehash: d803dba36b7790173b21dacb6cb34241f27dfb96
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65610968"
---
# <a name="tn058-mfc-module-state-implementation"></a>TN058: MFC modül durumu uygulaması

> [!NOTE]
> Aşağıdaki Teknik Not çevrimiçi belgelere ilk eklenmiştir beri güncelleştirilmemiş. Eski veya yanlış sonuç olarak, bazı yordamlar ve konular olabilir. En son bilgiler için bu konuyu çevrimiçi belge dizininde arama önerilir.

Bu teknik Not MFC "Modül durumu" yapıları uygulamasını açıklar. MFC kullanarak paylaşılan bir DLL DLL'lerden Modül durumu uygulaması anlaşılması önemlidir (veya OLE işlem sunucusu).

Bu Not okumadan önce "Yönetme durumu verileri, MFC modülleri için" başvuru [yeni belgeler oluşturma, Windows ve görünümler](../mfc/creating-new-documents-windows-and-views.md). Bu makale, önemli kullanım bilgilerini ve bu konu hakkında genel bilgiler içerir.

## <a name="overview"></a>Genel Bakış

MFC durum bilgilerini üç tür vardır: Modül durumu, işlem durumu ve iş parçacığı durumu. Bazen bu durum türleri birleştirilebilir. Örneğin, MFC'nin tanıtıcı eşlemeleri, hem yerel modülü hem de iş parçacığı yerel vardır. Bu, farklı eşlemeler her kendi iş parçacığı iki farklı modülü sağlar.

İşlem durumu ve iş parçacığı durumu benzerdir. Bu veri öğelerinin genel değişkenleri her zaman olmuştur, ancak için belirli bir işlemin belirli veya uygun Win32 desteklemek için veya uygun çoklu iş parçacığı destek için iş parçacığı için ihtiyacınız olan şey var. Bu öğeyi ve işlem ve iş parçacığı sınırları onaylamaz, istenen semantiği belirtilen veri öğesi sığacak kategorisini bağlıdır.

Küresel durumu ya da işlem yerel veya iş parçacığı yerel durumunu içeren modül durumu benzersizdir. Ayrıca, bu hızlı bir şekilde değiştirilebilir.

## <a name="module-state-switching"></a>Modül durumunu değiştirme

Her iş parçacığı "geçerli" veya "etkin" modülü durumuna yönelik bir işaretçi içerir (edilebileceği işaretçi MFC'nin iş parçacığı yerel durumu parçasıdır). Bu işaretçinin yürütme iş parçacığı bir OLE denetim veya DLL ya da bir OLE denetim geri bir uygulamaya çağırma çağıran bir uygulama gibi bir modül sınır geçtiğinde değiştirilir.

Geçerli modül durumunu çağırarak anahtarlanır `AfxSetModuleState`. Çoğunlukla, hiçbir zaman doğrudan API ile ilgilenecektir. MFC, çoğu durumda, çağırır, sizin için (WinMain, OLE giriş noktaları, en `AfxWndProc`vb..). Bu yazma statik olarak özel bir bağlama tarafından herhangi bir bileşeni gerçekleştirilir `WndProc`ve özel bir `WinMain` (veya `DllMain`) hangi Modül durumu geçerli olduğunu bilir. Bu kod DLLMODUL bakarak görebilirsiniz. CPP veya APPMODUL. CPP MFC\SRC dizinde.

Modül durumu ayarlayabilirsiniz ve daha sonra bunu yeniden değil istediğiniz nadir olarak rastlanıyor. Çoğu "kendi modülünüzü göndermek için" istediğiniz zaman geçerli bir durum ve bitirdikten sonra ardından "geri özgün içerik pop". Bu makro tarafından yapılır [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) ve özel sınıf `AFX_MAINTAIN_STATE`.

`CCmdTarget` Modül durumu geçiş desteklemek için özel özellikleri de vardır. Özellikle, bir `CCmdTarget` olduğu kök sınıfı, giriş noktaları OLE Otomasyonu nesnesi etkin ve OLE COM için kullanılır. Başka bir giriş noktası gibi sisteme kullanıma sunulan, bu giriş noktaları doğru Modül durumu ayarlamanız gerekir. Nasıl mu bir verilen `CCmdTarget` yanıtı, "oluşturulduğunda nedir"geçerli"modül durumunu hatırlar", sağlayacak şekilde ayarlayabilirsiniz "adlı sonraki olduğunda değer, geçerli Modül durumu anımsanacak" olan "doğru" Modül durumu ne olması gerektiğini bildirin. Sonuç olarak, Modül durumu, bir verilen `CCmdTarget` nesnedir ilişkili olduğu nesne, geçerli Modül durumu. InProc sunucusu yüklenirken, bir nesne oluşturma ve çağırma metotlarını basit bir örneğini alır.

1. DLL'nin OLE tarafından yüklenen kullanarak `LoadLibrary`.

2. `RawDllMain` ilk olarak adlandırılır. DLL için Modül durumu bilinen statik modülü durumuna ayarlar. Bu nedenle `RawDllMain` DLL'ye statik olarak bağlanır.

1. Bizim nesneyle ilişkili sınıf üreteci için oluşturucu çağrılır. `COleObjectFactory` türetilen `CCmdTarget` ve sonuç olarak, hangi modülü durumda örneği oluşturulduktan hatırlar. Bu önemlidir; nesneleri oluşturmak için sınıf üreteci sorulduğunda, artık geçerli hale getirmek için hangi modülü durumu biliyor.

4. `DllGetClassObject` sınıf üreteci almak için çağrılır. MFC, bu modül ile ilişkili sınıf Fabrika listesi arar ve onu döndürür.

5. `COleObjectFactory::XClassFactory2::CreateInstance` çağrılır. Bu işlev Modül durumu nesnesi oluşturup döndürmeden önce adım 3'te geçerli bir modül durumuna ayarlar. (ne zaman geçerli olanı `COleObjectFactory` örneklenmiş). İçine yapıldığını [METHOD_PROLOGUE](com-interface-entry-points.md).

1. Nesne oluşturulduğunda, çok uzun bir `CCmdTarget` türetme ve aynı şekilde `COleObjectFactory` anımsanacak hangi Modül durumu etkin, bu nedenle bu yeni nesne yok. Nesne geçmek için hangi modülü durumu bilir artık bunu ne zaman çağrılır.

1. İstemci, alınan OLE COM nesne üzerinde bir işlevi çağırır, `CoCreateInstance` çağırın. Nesne çağrıldığında kullandığı `METHOD_PROLOGUE` Modül durumu gibi geçiş yapmak için `COleObjectFactory` yapar.

Gördüğünüz gibi Modül durumu oluşturuldukları sırada nesneden nesneye yayılır. Modül durumu uygun şekilde ayarlanmış olması önemlidir. Ayarlanmazsa, DLL veya COM nesnenizin kötü, arama veya kendi kaynaklarını bulamıyor olabilir ya da sizin için berbat başka yöntemlerle de başarısız olabilir bir MFC uygulaması ile etkileşimde bulunabilir.

Belirli türdeki DLL'leri, özellikle "MFC uzantısı" DLL modülü durumda geçiş yapabilirim unutmayın, `RawDllMain` (aslında, bunlar genellikle bile yoksa bir `RawDllMain`). "Bunları kullanan uygulamada gerçekten olarak varsa" davranmaya hedeflenen olmasıdır. Çalışan uygulamada çok bir parçası ve bu uygulamanın genel durumunu değiştirmek için kendi amacınıza olur.

OLE denetimleri ve diğer DLL'leri çok farklıdır. Çağıran uygulamanın durumunu değiştirmek istemediğiniz; bunların çağrılması bir uygulama bir MFC uygulaması bile olmayabilir ve bu nedenle olabilir hiçbir durum değiştirmek için. Modül durumu geçiş bulunmuştur nedeni budur.

Gibi bir iletişim kutusunda, DLL başlatan bir DLL'den dışarı aktarılan işlevler için işlev başına aşağıdaki kodu ekleyin yapmanız gerekir:

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState())
```

Bu geçerli bir modül durumunu döndürüldüğü durumu ile değiştirir [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate) geçerli kapsamdaki sonuna kadar.

AFX_MODULE_STATE makrosu kullanılmıyorsa, DLL'lerdeki kaynakları ile ilgili sorunlar ortaya çıkar. Varsayılan olarak, kaynak şablonu yüklemek için ana uygulama kaynak tanıtıcısı MFC kullanır. Bu şablon, aslında DLL içinde depolanır. MFC modül durumu bilgilerini AFX_MODULE_STATE makro tarafından kullanılamayacağı değil, kök nedeni. MFC modül durumu kaynağı tanıtıcısı kurtarılır. Modül durumu geçiş değil, kullanılacak yanlış kaynak tanıtıcısı neden olur.

AFX_MODULE_STATE dll her işlevde beklemeye gerek yoktur. Örneğin, `InitInstance` MFC modül durumu önce otomatik olarak kayar çünkü AFX_MODULE_STATE olmadan uygulamayı MFC kod tarafından çağrılabilir `InitInstance` ve ardından geri sonra anahtarları `InitInstance` döndürür. Aynı tüm ileti eşlemesi işleyicileri için geçerlidir. Normal MFC DLL'leri gerçekte herhangi bir ileti yönlendirme önce Modül durumu otomatik olarak geçer bir özel ana pencere yordamı vardır.

## <a name="process-local-data"></a>Yerel verilerini işleme

Yerel verileri işlemek, Win32 DLL modelinin zorluğunu beri değil harika böyle bir sorun olmayacaktır. Win32 ' tüm DLL'leri bile birden çok uygulama tarafından yüklendiğinde, genel veri paylaşın. Bu, çok burada her DLL için DLL bağlayan her bir işlemdeki veri alanı ayrı bir kopyasını alır "gerçek" Win32 DLL veri modelinden farklıdır. Karmaşıklığa eklemek için bir Win32 DLL içinde yığında ayrılan veri aslında belirli (en az önceye sahipliği geçebileceği) işlemidir. Aşağıdaki veri ve kod göz önünde bulundurun:

```cpp
static CString strGlobal; // at file scope

__declspec(dllexport)
void SetGlobalString(LPCTSTR lpsz)
{
    strGlobal = lpsz;
}

__declspec(dllexport)
void GetGlobalString(LPCTSTR lpsz, size_t cb)
{
    StringCbCopy(lpsz, cb, strGlobal);
}
```

Yukarıdaki kod bir DLL içinde bulunuyorsa ve iki işlem A ve B (aslında iki örneği aynı uygulama olması olabilir) yüklenen DLL'i ne olacağını düşünün. Bir çağrı `SetGlobalString("Hello from A")`. Sonuç olarak, için bellek tahsis `CString` A. tutmak işlem bağlamında veriler aklınızda `CString` kendisi geneldir ve her iki A görünür ve B. Artık B çağırır `GetGlobalString(sz, sizeof(sz))`. B kümesi verileri görmek mümkün olacaktır. Win32 Win32 gibi işlemleri arasında hiçbir koruma sağladığından budur. İlk sorun olmasıdır; Çoğu durumda farklı bir uygulama tarafından ait olduğu kabul edilen genel verileri etkileyen bir uygulama için uygun değil.

Ek sorunlar vardır. Artık çıkar olduğunu varsayalım. A çıktığında, tarafından kullanılan bellek '`strGlobal`' dizesi sistemi için kullanılabilir yapılan — işlem A tarafından ayrılan tüm bellek işletim sistemi tarafından otomatik olarak diğer bir deyişle, serbest. Çünkü serbest değil `CString` yok Edicisi çağrılan; henüz adlı edilmemiş. Yalnızca serbest kendisine ayrılan uygulama Sahne bıraktığından. B adlı şimdi `GetGlobalString(sz, sizeof(sz))`, geçerli veri alamayabilir. Başka bir uygulama bu bellek başka bir şey kullanmış olabilirsiniz.

Açıkça bir sorun var. MFC 3.x iş parçacığı yerel depolama (TLS) olarak adlandırılan tekniği kullanılır. MFC 3.x, çağrılmaz olsa bile, Win32 altında gerçekten bir yerel işlem depolama dizini davranan bir TLS dizini ayrılamadı ve ardından başvuru, TLS dizinini temel alarak tüm verileri. Bu Win32 iş parçacığı-yerel verileri depolamak için kullanılan TLS dizini için benzer (aşağıda bu konu hakkında daha fazla bilgi için bkz:). Bu, işlem başına en az iki TLS dizinlerini kullanmaya her MFC DLL neden oldu. Birçok OLE Denetim dll (OCXs) yüklemek için hesap, (yalnızca 64 kullanılabilir yok) TLS dizinlerini dışında hızlıca çalıştırın. Ayrıca, tek bir yapı, tek bir yerde tüm bu verileri yerleştirmek MFC vardı. Bu çok Genişletilebilir değildi ve TLS dizinlerini kullanımı ile ilgili ideal değildi.

MFC 4.x sınıf şablonları, "sarmalamadan" geçici olarak yerel bir işlem olmalıdır verileri kümesiyle bu adresleri. Örneğin, yukarıda açıklanan sorun yazarak düzeltilmesi:

```cpp
struct CMyGlobalData : public CNoTrackObject
{
    CString strGlobal;
};
CProcessLocal<CMyGlobalData> globalData;

__declspec(dllexport)
void SetGlobalString(LPCTSTR lpsz)
{
    globalData->strGlobal = lpsz;
}

__declspec(dllexport)
void GetGlobalString(LPCTSTR lpsz, size_t cb)
{
    StringCbCopy(lpsz, cb, globalData->strGlobal);
}
```

MFC, bu iki adımda uygular. İlk olarak, Win32 üzerinde bir katman var. __Tls\*__  API'leri (**TlsAlloc**, **TlsSetValue**, **TlsGetValue**, vs.), kaç tane DLL'leri sahip olsun, işlem başına yalnızca iki TLS dizini kullanın. İkinci olarak, `CProcessLocal` şablonu, bu verilere erişmek için sağlanır. İşleci geçersiz olduğu ne göreceğiniz yukarıda sezgisel sözdizimi sağlar ->. Tarafından Sarmalanan tüm nesneleri `CProcessLocal` nesnesinden türetilmesi `CNoTrackObject`. `CNoTrackObject` bir alt düzey ayırıcı sağlar (**LocalAlloc**/**LocalFree**) ve sanal bir yıkıcı sağlayacak şekilde işlem sonlandırıldığında MFC otomatik olarak işlem yerel nesneleri yok edebilir. Ek temizleme gerekiyorsa özel bir yok edici bu tür nesneler olabilir. Derleyici katıştırılmış yok etmek için bir varsayılan yok Edicisi oluşturacak bu yana yukarıdaki örnekte, gerektirmeyen `CString` nesne.

Bu yaklaşım için ilgi çekici diğer avantajları vardır. Yalnızca tüm bunlar `CProcessLocal` nesneleri otomatik olarak yok gerekene kadar bunlar oluşturulur değil. `CProcessLocal::operator->` ilişkili nesne ilk zamana ve hiçbir erken örneği oluşturmak. Yukarıdaki örnekte, anlamına '`strGlobal`' dize oluşturulmadı kadar ilk kez `SetGlobalString` veya `GetGlobalString` çağrılır. Bazı durumlarda, bu DLL başlatma süresini kısaltmanıza yardımcı olabilir.

## <a name="thread-local-data"></a>İş parçacığı yerel veriler

Verileri belirli bir iş parçacığına yerel benzer yerel verileri işlemek için iş parçacığında yerel verilerin kullanılır. Diğer bir deyişle, bu verilere erişen her bir iş parçacığı için verileri ayrı bir örneğini gerekir. Bu kapsamlı eşitleme mekanizmaları yerine birden çok kez kullanılabilir. Veriler birden çok iş parçacığı tarafından paylaşılan gerekmez, bu mekanizmalar pahalı ve gereksiz olabilir. Yarışmayı varsayalım bir `CString` nesne (Yukarıdaki örnek gibi büyük). Bu iş parçacığı yerel ile sarmalama yapabiliyoruz bir `CThreadLocal` şablonu:

```cpp
struct CMyThreadData : public CNoTrackObject
{
    CString strThread;
};
CThreadLocal<CMyThreadData> threadData;

void MakeRandomString()
{
    // a kind of card shuffle (not a great one)
    CString& str = threadData->strThread;
    str.Empty();
    while (str.GetLength() != 52)
    {
        unsigned int randomNumber;
        errno_t randErr;
        randErr = rand_s(&randomNumber);

        if (randErr == 0)
        {
            TCHAR ch = randomNumber % 52 + 1;
            if (str.Find(ch) <0)
            str += ch; // not found, add it
        }
    }
}
```

Varsa `MakeRandomString` çağrıldı iki farklı iş parçacıklarından her "dize farklı şekillerde birbirleriyle engellemeden karışık". Bu olmadığından aslında bir `strThread` tek bir genel Örneğimiz yerine iş parçacığı başına örnek.

Bir başvuru yakalamak için nasıl kullanıldığını unutmayın `CString` yönelik bir kez yerine bir kez döngü yinelemesi. Döngü kodunun ile yazılmış `threadData->strThread` her yerde '`str`' kullanılır, ancak kod yürütme çok daha yavaş olur. Böyle başvurular Döngülerde oluştuğunda bir başvuru verileri önbelleğe almak idealdir.

`CThreadLocal` Sınıf şablonu mekanizmalarının aynısını kullanır, `CProcessLocal` yapar ve aynı uygulama teknikleri.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
