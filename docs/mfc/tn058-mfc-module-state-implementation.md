---
description: 'Hakkında daha fazla bilgi edinin: TN058: MFC modül durumu uygulama'
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
ms.openlocfilehash: c4b300b9aa184e9fa1c6cfd5a8cf668d163d85ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214786"
---
# <a name="tn058-mfc-module-state-implementation"></a>TN058: MFC Modül Durumu Uygulaması

> [!NOTE]
> Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

Bu teknik notta MFC "modül durumu" yapılarının uygulanması açıklanmaktadır. Modül durumu uygulamasının anlaşılmasına, MFC paylaşılan DLL 'Lerinin bir DLL 'den (veya OLE işlem içi sunucuda) kullanılması önemlidir.

Bu notun okumadan önce, [yeni belgeler, pencereler ve görünümler oluşturma](../mfc/creating-new-documents-windows-and-views.md)bölümünde "MFC modüllerinin durum verilerini yönetme" bölümüne bakın. Bu makale, bu konudaki önemli kullanım bilgilerini ve genel bakış bilgilerini içerir.

## <a name="overview"></a>Genel Bakış

Üç tür MFC durum bilgisi vardır: modül durumu, Işlem durumu ve Iş parçacığı durumu. Bazen bu durum türleri birleştirilebilir. Örneğin, MFC 'nin tanıtıcı eşlemeleri hem modül yerel hem de iş parçacığı yereldir. Bu, iki farklı modülün iş parçacıklarında farklı haritalara sahip olmasını sağlar.

İşlem durumu ve Iş parçacığı durumu benzerdir. Bu veri öğeleri, geleneksel olarak genel değişkenlere sahip olan, ancak uygun Win32s desteği veya uygun çoklu iş parçacığı kullanımı için belirli bir işlem veya iş parçacığına özgü olması gereken öğelerdir. Verilen bir veri öğesi hangi kategoriye göre değişir bu öğeye ve işlem ve iş parçacığı sınırlarına göre istenen semantiklerine bağlıdır.

Modül durumu, gerçek anlamda genel durumu veya yerel iş parçacığı yerel durumunu içerebilen bir durumdur. Ayrıca, bu hızlı bir şekilde değiştirilebilir.

## <a name="module-state-switching"></a>Modül durumu değiştirme

Her iş parçacığı "geçerli" veya "etkin" modül durumunun bir işaretçisini içerir (Bu, işaretçi, MFC 'nin iş parçacığı yerel durumunun bir parçasıdır). Bu işaretçi, yürütme iş parçacığı bir OLE denetimine veya DLL 'ye çağrı yapan bir uygulama ya da bir uygulamaya geri çağıran OLE denetimi gibi bir modül sınırı geçtiğinde değişir.

Geçerli modül durumu çağırarak çağrılır `AfxSetModuleState` . Çoğu bölüm için, API ile doğrudan hiçbir işlem yapmanız hiçbir şekilde hiçbir şekilde uğraşacaktır. Çoğu durumda MFC bunu sizin için çağıracaktır (WinMain, OLE giriş noktaları, `AfxWndProc` vb.). Bu, özel olarak bir özel olarak bağlantı kurarak yazdığınız herhangi bir bileşende `WndProc` ve `WinMain` `DllMain` hangi modül durumunun geçerli olması gerektiğini bilen özel bir (veya) olarak yapılır. Bu kodu, DLLMODÜL bölümüne bakarak görebilirsiniz. CPP veya APPMODÜL. MFC\SRC dizinindeki CPP.

Modül durumunu ayarlamak ve sonra geri ayarlamak istemezsiniz. Kendi modülünüzü geçerli bir şekilde "göndermek" istediğiniz zaman, ardından, tamamladıktan sonra özgün bağlamı geri "pop". Bu, makro [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) ve özel sınıf tarafından yapılır `AFX_MAINTAIN_STATE` .

`CCmdTarget` Modül durumu geçişini desteklemek için özel özelliklere sahiptir. Özellikle, `CCmdTarget` OLE Otomasyonu ve ole com giriş noktaları için kullanılan kök sınıftır. Sisteme açık olan diğer herhangi bir giriş noktası gibi, bu giriş noktaları doğru modül durumunu ayarlamış olmalıdır. `CCmdTarget`"Doğru" modül durumunun yanıt olması gereken "," geçerli "modül durumunun ne zaman oluşturulduğunu (" hatırlanır "), daha sonra çağrıldığında geçerli modül durumunu" anımsanan "değerine ayarlayabilmesini sağlar. Sonuç olarak, belirli bir nesnenin ilişkilendirildiği modül durumu, `CCmdTarget` nesne oluşturulduğunda geçerli olan modül durumudur. INPROC sunucusu yükleme, nesne oluşturma ve yöntemlerini çağırma hakkında basit bir örnek alın.

1. DLL, kullanılarak OLE tarafından yüklenir `LoadLibrary` .

1. `RawDllMain` İlk olarak çağırılır. Modül durumunu DLL için bilinen statik modül durumuna ayarlar. Bu nedenle `RawDllMain` , dll 'ye statik olarak bağlanır.

1. Nesnemiz ile ilişkili sınıf fabrikası için Oluşturucu çağırılır. `COleObjectFactory` , ' den türetilir `CCmdTarget` ve sonuç olarak, hangi modül durumunun örneği olduğunu anımsar. Bu önemlidir: sınıf fabrikasının nesne oluşturması istendiğinde, şimdi geçerli hale getirmek için modül durumunu biliyor.

1. `DllGetClassObject` sınıf fabrikası elde etmek için çağırılır. MFC bu modülle ilişkili sınıf fabrikası listesini arar ve döndürür.

1. `COleObjectFactory::XClassFactory2::CreateInstance` çağırılır. Nesneyi oluşturmadan ve döndürmeden önce, bu işlev modül durumunu 3. adımda geçerli olan modül durumuna ayarlar (örneği oluşturulduğu sırada geçerli olan `COleObjectFactory` ). Bu, [METHOD_PROLOGUE](com-interface-entry-points.md)içinde yapılır.

1. Nesne oluşturulduğunda, `CCmdTarget` Bu bir türev olur ve aynı `COleObjectFactory` Modül durumunun etkin olduğunu hatırladığı şekilde aynı şekilde, bu yeni nesneyi yapar. Artık nesnesi, her çağrıldığında hangi modül durumunun geçiş olduğunu bilir.

1. İstemci, çağrısından aldığı OLE COM nesnesinde bir işlev çağırır `CoCreateInstance` . Nesne çağrıldığında, `METHOD_PROLOGUE` modül durumunu olduğu gibi değiştirmek için kullanır `COleObjectFactory` .

Gördüğünüz gibi, modül durumu nesnesinden nesnesine yayılır ve oluşturulur. Modül durumunun uygun şekilde ayarlanması önemlidir. Ayarlanmamışsa, DLL 'niz veya COM nesneniz onu çağıran bir MFC uygulamasıyla kötü bir şekilde etkileşim kurabilir veya kendi kaynaklarını bulamamasına veya diğer hatalı yollarla başarısız olabilir.

Özellikle "MFC uzantısı" dll 'lerinin, belirli tür dll 'lerin `RawDllMain` (aslında genellikle olmasa bile) modül durumunu değiştirmediğini unutmayın `RawDllMain` . Bunun nedeni, bunları kullanan uygulamada gerçekten mevcut olduklarından "olduğu gibi" davranmaya yöneliktir. Bunlar, uygulamasının çalıştığı uygulamanın bir parçasıdır ve bu uygulamanın genel durumunu değiştirmek sizin için tasarlanmıştır.

OLE denetimleri ve diğer dll 'Ler çok farklıdır. Çağıran uygulamanın durumunu değiştirmek istemler; Bunları çağıran uygulama, bir MFC uygulaması bile olmasa da, değiştirilecek bir durum olmayabilir. Bu, modül durumu geçişinin nasıl oluşturulduğu nedenidir.

Dll 'inizdeki bir iletişim kutusu Başlatan gibi bir DLL 'den içe aktarılmış işlevler için, işlevin başlangıcına aşağıdaki kodu eklemeniz gerekir:

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState())
```

Bu, geçerli modülün durumunu geçerli kapsamın sonuna kadar [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate) öğesinden döndürülen durum ile değiştirir.

AFX_MODULE_STATE makrosu kullanılmazsa, dll 'Lerdeki kaynaklarla ilgili sorunlar oluşur. Varsayılan olarak, MFC kaynak şablonunu yüklemek için ana uygulamanın kaynak tanıtıcısını kullanır. Bu şablon aslında DLL 'de depolanır. Kök nedeni, MFC 'nin modül durumu bilgilerinin AFX_MODULE_STATE makrosu tarafından geçmemelidir. Kaynak tanıtıcısı, MFC 'nin modül durumundan kurtarıldı. Modül durumunun değiştirilmemesi yanlış kaynak tanıtıcısının kullanılmasına neden olur.

AFX_MODULE_STATE DLL içindeki her işleve yerleştirilmeye gerek yoktur. Örneğin, `InitInstance` MFC otomatik olarak modül durumunu otomatik olarak kaydığı `InitInstance` ve sonra geri döndürdüğü için AFX_MODULE_STATE olmadan uygulamadaki MFC kodu tarafından çağrılabilir `InitInstance` . Tüm ileti eşleme işleyicileri için de aynı değer geçerlidir. Normal MFC DLL 'Lerinin aslında herhangi bir iletiyi yönlendirmeden önce modül durumunu otomatik olarak yönlendiren özel bir ana pencere prosedürü vardır.

## <a name="process-local-data"></a>Yerel verileri işle

İşlem yerel verileri, bu tür harika bir sorun değil, Win32s DLL modelinin zorluğunu karşılamıyor. Win32s içinde, tüm dll 'Ler, birden çok uygulama tarafından yüklense bile genel verilerini paylaşır. Bu, her DLL 'nin DLL 'ye bağlanan her bir işlemde veri alanının ayrı bir kopyasını aldığı "gerçek" Win32 DLL veri modelinden çok farklıdır. Karmaşıklığa eklemek için, bir Win32s DLL 'de yığında ayrılan veriler gerçek işleme özgüdür (en azından sahipliğin ulaştığı kadar). Aşağıdaki verileri ve kodu göz önünde bulundurun:

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

Yukarıdaki kod bir DLL 'de bulunuyorsa ve bu DLL, A ve B iki işlem tarafından yüklenirse (aslında aynı uygulamanın iki örneği olabilir) ne olacağını göz önünde bulundurun. Bir çağrı `SetGlobalString("Hello from A")` . Sonuç olarak, `CString` a işleminin bağlamındaki veriler için bellek ayrılır. `CString` kendisinin geneldir olduğunu ve hem a hem de B için görünür olduğunu aklınızda bulundurun. Şimdi B çağrısı `GetGlobalString(sz, sizeof(sz))` . B, bir küme tarafından ayarlanan verileri görebilir. Bunun nedeni, Win32s 'in Win32 gibi süreçler arasında hiçbir koruma sunmadığından kaynaklanır. Bu ilk sorundur; Çoğu durumda, bir uygulamanın farklı bir uygulamaya ait olduğu kabul edilen genel verileri etkilemesini tercih edilmez.

Ek sorunlar da vardır. Şimdi bir çıkış olduğunu varsayalım. Bir çıkış olduğunda, ' ' dizesi tarafından kullanılan bellek `strGlobal` sistem için kullanılabilir — yani, işlem tarafından ayrılan tüm bellek işletim sistemi tarafından otomatik olarak serbest bırakılır. Yok edicinin çağrılmakta olduğu için serbest bırakılmamıştır `CString` ; henüz çağrılmadı. Yalnızca onu ayırmış olan uygulama sahneyi bıraktı olduğundan serbest bırakılır. B çağrılırsa `GetGlobalString(sz, sizeof(sz))` , geçerli verileri alamaz. Başka bir uygulama bu belleği başka bir şey için kullanmış olabilir.

Açık bir sorun var. MFC 3. x, iş parçacığı yerel depolaması (TLS) adlı bir teknik kullandı. MFC 3. x, bu, çağrılmayan ve bu TLS dizinine göre tüm verilere başvurmasına rağmen, Win32s 'in altındaki bir TLS dizinini ayırır. Bu, Win32 üzerinde iş parçacığı yerel verilerini depolamak için kullanılan TLS dizinine benzerdir (Bu konu hakkında daha fazla bilgi için aşağıya bakın). Bu, her MFC DLL 'nin işlem başına en az iki TLS dizininden yararlanmasına neden oldu. Birçok OLE denetim dll 'Sini (OCXs) yüklemek için hesap kullandığınızda, TLS dizininden hızlı bir şekilde çalışmaya (yalnızca 64 kullanılabilir) sahip olursunuz. Ayrıca, MFC 'nin tüm bu verileri tek bir yapıda tek bir yerde yerleştirmesinin gerekiyordu. Bu çok genişletilemez ve TLS dizinlerinin kullanımıyla ilgili olarak ideal değildir.

MFC 4. x bunu bir sınıf şablonları kümesiyle adresleyerek yerel olarak işlem yapmanız gereken verilerin etrafında "sarmalama" yapabilirsiniz. Örneğin, yukarıda bahsedilen sorun yazılarak düzeltilebilir:

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

MFC bunu iki adımda uygular. İlk olarak, bir işlem başına yalnızca iki TLS dizini kullanan __Win32 \* TLS__ API 'Lerinin (**TlsAlloc**, **TlsSetValue**, **TlsGetValue**, vb.) en üstünde bir katman vardır. İkinci olarak, `CProcessLocal` şablon bu verilere erişmek için sağlanır. Yukarıda gördüğünüz sezgisel sözdizimine izin veren operator-> geçersiz kılar. Tarafından Sarmalanan tüm nesneler `CProcessLocal` öğesinden türetilmelidir `CNoTrackObject` . `CNoTrackObject`, bir alt düzey ayırıcı (**LocalAlloc** / **LocalFree**) ve bir sanal yıkıcı sağlar ve böylece işlem sonlandırıldığında MFC yerel nesneleri otomatik olarak yok edebilir. Ek temizleme gerekliyse, bu tür nesneler özel bir yıkıcıya sahip olabilir. Derleyici, gömülü nesneyi yok etmek için varsayılan bir yıkıcı oluşturacak olduğundan, yukarıdaki örnek bir tane gerektirmez `CString` .

Bu yaklaşımın ilginç avantajları vardır. Tüm `CProcessLocal` nesneler otomatik olarak yok edilmez, bunlar gerekene kadar oluşturulur. `CProcessLocal::operator->` ilk çağrılışında ilişkili nesneyi örnekleyin ve daha erken olmaz. Yukarıdaki örnekte bu, ' `strGlobal` ' dizesinin ilk kez `SetGlobalString` veya çağrılıncaya kadar oluşturulamadığından emin olur `GetGlobalString` . Bazı örneklerde bu, DLL başlatma zamanının azaltılmasına yardımcı olabilir.

## <a name="thread-local-data"></a>İş parçacığı yerel verileri

Yerel verileri işlemeye benzer şekilde, iş parçacığı yerel verileri, verilerin belirli bir iş parçacığında yerel olması gereken durumlarda kullanılır. Yani, bu veriye erişen her iş parçacığı için verilerin ayrı bir örneğine ihtiyacınız vardır. Bu, kapsamlı eşitleme mekanizmaları yerine birçok kez kullanılabilir. Verilerin birden çok iş parçacığı tarafından paylaşılması gerekmiyorsa, bu tür mekanizmalar pahalı ve gereksiz olabilir. Bir `CString` nesnemiz olduğunu varsayalım (Yukarıdaki örneğe benzer şekilde). Bir şablon ile sarmalayarak BT iş parçacığını yerelyapabiliriz `CThreadLocal` :

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

`MakeRandomString`İki farklı iş parçacığından çağrılırsa, her biri dizeyi, diğerini etkilemeden farklı yollarla "karıştı". Bunun nedeni, `strThread` yalnızca bir genel örnek yerine iş parçacığı başına bir örnek olması olabilir.

Bir başvurunun `CString` her döngü yinelemesinde bir kez yerine adresi yakalamak için nasıl kullanıldığını aklınızda yapın. Döngü kodu `threadData->strThread` her yerde ' `str` ' kullanılmış olabilir, ancak kod yürütme sırasında çok daha yavaş olabilir. Döngüler içinde bu tür başvurular gerçekleştiğinde veriye bir başvuruyu önbelleğe almak en iyisidir.

`CThreadLocal`Sınıf şablonu, `CProcessLocal` ve aynı uygulama teknikleriyle aynı mekanizmaların aynısını kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
