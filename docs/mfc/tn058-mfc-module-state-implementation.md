---
title: 'TN058: MFC Modül Durumu Uygulaması'
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
ms.openlocfilehash: b64fb6b97474007c44a2124315e83e1ac119f9ec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366616"
---
# <a name="tn058-mfc-module-state-implementation"></a>TN058: MFC Modül Durumu Uygulaması

> [!NOTE]
> Aşağıdaki teknik not, çevrimiçi belgelere ilk olarak eklenmediğinden beri güncelleştirilemedi. Sonuç olarak, bazı yordamlar ve konular güncel veya yanlış olabilir. En son bilgiler için, çevrimiçi belge dizini ilgi alanı için arama nız önerilir.

Bu teknik not, MFC "modül durumu" yapılarının uygulanmasını açıklar. Modül durumu uygulamasının anlaşılması, Bir DLL'den (veya OLE işlem sunucusundan) MFC paylaşılan DL'leri kullanmak için çok önemlidir.

Bu notu okumadan önce, [Yeni Belgeler, Windows ve Görünümler Oluştururken](../mfc/creating-new-documents-windows-and-views.md)"MFC Modüllerinin Durum Verilerini Yönetme"ye bakın. Bu makalede, önemli kullanım bilgileri ve bu konuda genel bakış bilgileri içerir.

## <a name="overview"></a>Genel Bakış

Üç tür MFC durumu bilgisi vardır: Modül Durumu, İşlem Durumu ve İş Parçacığı Durumu. Bazen bu durum türleri birleştirilebilir. Örneğin, MFC'nin tutamak haritaları hem modül yerel hem de iş parçacığı yereldir. Bu, iki farklı modülün her bir iş parçacığında farklı haritalara sahip olmasını sağlar.

İşlem Durumu ve İş Parçacığı Durumu benzerdir. Bu veri öğeleri geleneksel olarak küresel değişkenler olan, ancak uygun Win32s desteği veya uygun çok iş parçacığı desteği için belirli bir işleme veya iş parçacığına özgü olması gereken şeylerdir. Belirli bir veri öğesinin hangi kategoriye uyduğu, işlem ve iş parçacığı sınırları açısından o öğeye ve istenen semantiklere bağlıdır.

Modül Durumu, gerçek anlamda küresel durum veya işlem yerel veya iş parçacığı yerel devlet içerebileceği benzersizdir. Buna ek olarak, hızlı bir şekilde değiştirilebilir.

## <a name="module-state-switching"></a>Modül Durum Anahtarlama

Her iş parçacığı "geçerli" veya "etkin" modül durumuna bir işaretçi içerir (şaşırtıcı değil, işaretçi MFC iş parçacığı yerel durumunun bir parçasıdır). Yürütme iş parçacığı, OLE Denetimi'ne veya DLL'ye çağıran bir uygulama veya bir uygulama içine geri çağıran bir OLE Denetimi gibi bir modül sınırını geçtiğinde bu işaretçi değiştirilir.

Geçerli modül durumu '. `AfxSetModuleState` Çoğunlukla, doğrudan API ile uğraşmak asla. MFC, birçok durumda, sizin için (WinMain, OLE giriş `AfxWndProc`noktaları, vb) arayacak. Bu, özel bir ve hangi modül durumunun `WndProc`güncel olması `WinMain` gerektiğini `DllMain`bilen özel (veya) bir özel (veya) statik olarak bağlanarak yazdığınız herhangi bir bileşende yapılır. DLLMODUL bakarak bu kodu görebilirsiniz. CPP veya APPMODUL. MFC\SRC dizininde CPP.

Modül durumunu ayarlamak ve sonra geri ayarlamak istediğiniz nadirdir. Çoğu zaman geçerli bir olarak kendi modül durumu "itmek" ve sonra, sonra, bittikten sonra, "pop" orijinal bağlam geri istiyorum. Bu makro [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) ve özel sınıf `AFX_MAINTAIN_STATE`tarafından yapılır.

`CCmdTarget`modül durumu anahtarlama destekleyen özel özelliklere sahiptir. Özellikle, a `CCmdTarget` OLE otomasyonu ve OLE COM giriş noktaları için kullanılan kök sınıfıdır. Sisteme maruz kalan diğer giriş noktaları gibi, bu giriş noktaları da doğru modül durumunu ayarlamalıdır. Verilen `CCmdTarget` bir "doğru" modül durumunun ne olması gerektiğini nasıl bilir? Sonuç olarak, belirli `CCmdTarget` bir nesnenin ilişkili olduğu modül durumu, nesne oluşturulduğunda geçerli olan modül durumudur. INPROC sunucusuyükleme, nesne oluşturma ve yöntemlerini arama gibi basit bir örnek alın.

1. DLL, OLE tarafından `LoadLibrary`'.

1. `RawDllMain`önce denir. Modül durumunu DLL için bilinen statik modül durumuna ayarlar. Bu nedenle `RawDllMain` statik DLL'ye bağlıdır.

1. Nesnemizle ilişkili sınıf fabrikasının oluşturucusu denir. `COleObjectFactory`türetilir `CCmdTarget` ve sonuç olarak, hangi modül durumunda anında olduğunu hatırlar. Bu önemlidir — sınıf fabrikasından nesneler oluşturması istendiğinde, artık hangi modül durumunun geçerli olacağını bilir.

1. `DllGetClassObject`sınıf fabrika elde etmek için denir. MFC, bu modülle ilişkili sınıf fabrika listesini arar ve döndürür.

1. `COleObjectFactory::XClassFactory2::CreateInstance`denir. Nesneyi oluşturmadan ve döndürmeden önce, bu işlev modül durumunu adım 3'te geçerli olan modül `COleObjectFactory` durumuna ayarlar (anlık olarak oluşturulduğunda geçerli olan) Bu [METHOD_PROLOGUE](com-interface-entry-points.md)içinde yapılır.

1. Nesne oluşturulduğunda, o da `CCmdTarget` bir türev dir `COleObjectFactory` ve aynı şekilde hangi modül durumunun etkin olduğu hatırlanır, bu yeni nesne de öyle. Artık nesne, çağrıldığında hangi modül durumuna geçilmeye cereyan edilsin.

1. İstemci, `CoCreateInstance` çağrısından aldığı OLE COM nesnesi üzerinde bir işlev çağırır. Nesne çağrıldığında, `METHOD_PROLOGUE` modül durumunu tıpkı yaptığı `COleObjectFactory` gibi değiştirmek için kullanılır.

Gördüğünüz gibi, modül durumu oluşturuldukça nesneden nesneye yayılır. Modül durumunun uygun şekilde ayarlı olması önemlidir. Ayarlanmazsa, DLL veya COM nesneniz onu çağıran bir MFC uygulamasıyla kötü etkileşimde bulunabilir veya kendi kaynaklarını bulamayabilir veya başka sefil şekillerde başarısız olabilir.

DLs belirli türde, özellikle "MFC Extension" DLLs kendi `RawDllMain` modül durumu geçiş olmadığını unutmayın (aslında, `RawDllMain`genellikle bile yok). Bunun nedeni, onları kullanan uygulamada gerçekte mevcut oldukları "sanki" gibi bir şekilde nasıl bir şekilde nasıl bir şekilde iyi bir şekilde bulunmaları gerektiğidir. Onlar çok çalışan uygulamanın bir parçasıdır ve bu uygulamanın küresel durumunu değiştirmek için niyetleri olduğunu.

OLE Kontrolleri ve diğer DL'ler çok farklıdır. Arama uygulamasının durumunu değiştirmek istemezler; onları çağıran uygulama bile bir MFC uygulaması olmayabilir ve bu nedenle değiştirmek için hiçbir durum olabilir. Modül durum anahtarlamasının icat edilmiş olmasının nedeni budur.

DLL'nizde bir iletişim kutusu başlatan bir DLL'den dışa aktarılan işlevler için işlevin başına aşağıdaki kodu eklemeniz gerekir:

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState())
```

Bu, geçerli modül durumunu [AfxGetStaticModuleState'den](reference/extension-dll-macros.md#afxgetstaticmodulestate) dönen durumla, geçerli kapsamın sonuna kadar değiştirir.

AFX_MODULE_STATE makrosu kullanılmazsa, DL'lerde kaynaklarla ilgili sorunlar oluşur. Varsayılan olarak, MFC kaynak şablonu yüklemek için ana uygulamanın kaynak tutamacını kullanır. Bu şablon aslında DLL'de depolanır. Temel nedeni, MFC'nin modül durumu bilgilerinin AFX_MODULE_STATE makrotarafından değiştirilmemiş olmasıdır. Kaynak tutamacı MFC'nin modül durumundan kurtarılır. Modül durumunu değiştirmemek, yanlış kaynak tanıtıcısının kullanılmasına neden olur.

AFX_MODULE_STATE DLL'deki her işleve konması gerekmez. Örneğin, `InitInstance` MFC modül durumunu önce otomatik olarak kaydırDığı `InitInstance` ve döndükten sonra `InitInstance` değiştirdiği için, uygulamadaki MFC kodu tarafından AFX_MODULE_STATE çağrılabilir. Aynı durum tüm ileti eşlemi işleyicileri için de geçerlidir. Normal MFC DLL'ler aslında herhangi bir iletiyi yönlendirmeden önce modül durumunu otomatik olarak anahtarlayan özel bir ana pencere yordamına sahiptir.

## <a name="process-local-data"></a>Yerel Verileri İşlem

Win32s DLL modelinin zorluğu olmasaydı yerel verileri işlemek bu kadar büyük bir endişe kaynağı olmazdı. Win32'lerde tüm DL'ler, birden fazla uygulama tarafından yüklendiğinde bile küresel verilerini paylaşır. Bu, her DLL'nin DLL'ye iliştirilen her işlemde kendi veri alanının ayrı bir kopyasını aldığı "gerçek" Win32 DLL veri modelinden çok farklıdır. Karmaşıklık eklemek için, bir Win32s DLL yığın üzerinde ayrılan veri aslında işlem özel (en azından kadarıyla mülkiyet gider). Aşağıdaki verileri ve kodu göz önünde bulundurun:

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

Yukarıdaki kodun bir DLL'de bulunması ve DLL'nin A ve B iki işlemi yle yüklendiğini düşünün (aslında aynı uygulamanın iki örneği olabilir). Bir `SetGlobalString("Hello from A")`arama. Sonuç olarak, bellek a. `CString` kendisi küresel ve hem A hem de `CString` B tarafından görülebilir olduğunu unutmayın süreci Bağlamında veri için ayrılmıştır. Şimdi B `GetGlobalString(sz, sizeof(sz))`çağırır . B, A kümesinin verilerini görebilir. Bunun nedeni Win32s'nin Win32 gibi süreçler arasında hiçbir koruma sunmasıdır. Bu ilk sorun; birçok durumda, bir uygulamanın farklı bir uygulamaya ait olduğu düşünülen genel verileri etkilemesi istenmez.

Başka sorunlar da var. Diyelim ki A şimdi çıkıyor. A çıktığında, ' '`strGlobal`dizesi tarafından kullanılan bellek sistem için kullanılabilir hale getirilir — yani A işlemi tarafından ayrılan tüm bellek işletim sistemi tarafından otomatik olarak serbest bırakılır. `CString` Yıkıcı çağrıldığı için serbest bırakılmaz; Henüz çağrılmadı. Yalnızca onu tahsis eden uygulama sahneyi terk ettiği için serbest bırakılır. Şimdi B `GetGlobalString(sz, sizeof(sz))`aradı, geçerli veri almayabilir. Başka bir uygulama başka bir şey için bu belleği kullanmış olabilir.

Belli ki bir sorun var. MFC 3.x iş parçacığı yerel depolama (TLS) adı verilen bir teknik kullandı. MFC 3.x, Win32s altında gerçekten bir süreç-yerel depolama dizini olarak hareket eden bir TLS endeksi tahsis edecek, bu çağrılmasa bile ve daha sonra bu TLS endeksine dayalı tüm verilere başvurur. Bu, iş parçacığı yerel verilerini Win32'de depolamak için kullanılan TLS dizinine benzer (bu konuda daha fazla bilgi için aşağıya bakın). Bu, her MFC DLL'nin işlem başına en az iki TLS endeksini kullanmasına neden oldu. Birçok OLE Control DLl (OCX) yükleme için hesap yaptığınızda, hızlı bir şekilde TLS endeksleri (sadece 64 kullanılabilir) biter. Buna ek olarak, MFC tüm bu verileri tek bir yerde, tek bir yapıda yerleştirmek zorunda kaldı. Çok genişletilebilir değildi ve TLS endekslerinin kullanımı açısından ideal değildi.

MFC 4.x, yerel işlem olması gereken verilerin etrafına "sarabileceğiniz" sınıf şablonları kümesiyle bu adresi ele alıyor. Örneğin, yukarıda belirtilen sorun yazılarak giderilebilir:

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

MFC bunu iki adımda uygular. İlk olarak, win32 __Tls\* __ API'lerinin **(TlsAlloc,** **TlsSetValue,** **TlsGetValue,** vb.) üzerinde, kaç DL'ye sahip olursanız olun, işlem başına sadece iki TLS dizin kullanan bir katman vardır. İkinci olarak, `CProcessLocal` şablon bu verilere erişmek için sağlanır. Yukarıda gördüğünüz sezgisel sözdizimini sağlayan operatör > geçersiz kılar. Tarafından `CProcessLocal` sarılmış tüm nesneler. `CNoTrackObject` `CNoTrackObject`daha düşük seviyeli bir ayırıcı **(LocalAlloc**/**LocalFree)** ve MFC işlemi sonlandırıldığında otomatik olarak işlem yerel nesneleri yok edebilir gibi bir sanal yıkıcı sağlar. Ek temizleme gerekiyorsa, bu tür nesnelerin özel bir yıkıcısı olabilir. Derleyici katıştırılmış `CString` nesneyi yok etmek için varsayılan bir yıkıcı oluşturacağı için yukarıdaki örnekte bir tane gerekmez.

Bu yaklaşımın diğer ilginç avantajları vardır. Tüm `CProcessLocal` nesneler otomatik olarak yok etmekle kalmıyor, aynı şekilde ihtiyaç duyulana kadar oluşturulmuyor. `CProcessLocal::operator->`ilişkili nesneyi ilk çağrıldığında anında ve daha önce değil. Yukarıdaki örnekte, ''`strGlobal`dizesi ilk kez `SetGlobalString` yapılanmayacak `GetGlobalString` veya çağrılmayacak anlamına gelir. Bazı durumlarda, bu DLL başlangıç süresini azaltmaya yardımcı olabilir.

## <a name="thread-local-data"></a>İş Parçacığı Yerel Veriler

Yerel verileri işlemeye benzer şekilde, verilerin belirli bir iş parçacığına yerel olması gerektiğinde iş parçacığı yerel verileri kullanılır. Diğer bir süre, bu verilere erişen her iş parçacığı için ayrı bir veri örneği gerekir. Bu, kapsamlı eşitleme mekanizmaları yerine birçok kez kullanılabilir. Verilerin birden çok iş parçacığı tarafından paylaşılması gerekmiyorsa, bu tür mekanizmalar pahalı ve gereksiz olabilir. Bir `CString` nesnemiz olduğunu varsayalım (yukarıdaki örneğe çok benzer). Bir `CThreadLocal` şablonla sararak iş parçacığı yerel yapabiliriz:

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

İki `MakeRandomString` farklı iş parçacığı çağrıldıysa, her biri diğerini karıştırmadan dizeyi farklı şekillerde "karıştırır". Bunun nedeni, iş `strThread` parçacığı başına sadece bir genel örnek yerine bir örnek olmasıdır.

Bir başvurunun, döngü yinelemesi başına bir kez yerine adresi bir kez yakalamak için nasıl kullanıldığına `CString` dikkat edin. Döngü kodu `threadData->strThread` her yerde '`str`' ' ile yazılmış olabilir, ancak kod yürütme çok daha yavaş olacaktır. Bu tür başvurular döngüler halinde gerçekleştiğinde verilere bir başvuru önbelleğe almak en iyisidir.

Sınıf `CThreadLocal` `CProcessLocal` şablonu, aynı mekanizmaları ve aynı uygulama tekniklerini kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
