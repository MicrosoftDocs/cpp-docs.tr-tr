---
title: "TN058: MFC modül durumu uygulaması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.implementation
dev_langs: C++
helpviewer_keywords:
- thread state [MFC]
- module states [MFC], managing state data
- TN058
- MFC, managing state data
- module states [MFC], switching
- DLLs [MFC], module states
- process state [MFC]
ms.assetid: 72f5b36f-b3da-4009-a144-24258dcd2b2f
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ed7bc195c771026ff3e58d53f9e3936791810e76
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="tn058-mfc-module-state-implementation"></a>TN058: MFC Modül Durumu Uygulaması
> [!NOTE]
>  İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.  
  
 Bu teknik Not MFC "Modül durumu" yapıları uygulamasını açıklar. Paylaşılan DLL DLL'lerden MFC kullanma için Modül durumu uygulaması anlaşılması önemlidir (veya OLE işlemdeki sunucu).  
  
 Bu Not okumadan önce "Yönetme durumu verileri, MFC modülleri için" başvuru [oluşturma yeni belgeler, pencereler ve görünümler](../mfc/creating-new-documents-windows-and-views.md). Bu makalede önemli kullanım bilgileri ve bu konu hakkında genel bakış bilgileri içerir.  
  
## <a name="overview"></a>Genel Bakış  
 MFC durum bilgilerini üç tür vardır: Modül durumu, işlem durumu ve iş parçacığı durumu. Bazen bu durum türleri birleştirilebilir. Örneğin, hem yerel modülü hem de iş parçacığı yerel MFC'nin tanıtıcı eşlemeleri vardır. Bu, farklı eşlemeleri her kendi iş parçacığı iki farklı modülleri sağlar.  
  
 İşlem durumu ve iş parçacığı durumu benzerdir. Bu veri öğeleri genel değişkenler her zaman olmuştur, ancak verilen bir işlemi belirli veya uygun Win32 desteklemek için veya uygun çoklu iş parçacığı destek için iş parçacığı için ihtiyacınız olan noktalardır. Bu öğe ve kendi istenen semantiği işlemi ve iş parçacığı sınırları açısından belirli veri öğesi uygun kategori bağlıdır.  
  
 Modül durumu gerçekten genel durum ya da işlem yerel veya iş parçacığı yerel durumunu içeren benzersizdir. Ayrıca, hızlı bir şekilde değiştirilebilir.  
  
## <a name="module-state-switching"></a>Modül durumu değiştirme  
 Her iş parçacığı "geçerli" veya "etkin" modülünün durumunu gösteren bir işaretçi içeriyor (edilebileceği işaretçinin MFC'nin iş parçacığı yerel durumu parçasıdır). Bu işaretçinin yürütme iş parçacığı bir OLE denetimi veya DLL ya da bir OLE denetim geri bir uygulamaya çağırma çağırma bir uygulama gibi bir modül sınır geçtiğinde değiştirilir.  
  
 Geçerli modül durumunu çağırarak anahtarlanır **AfxSetModuleState**. Çoğunlukla, hiçbir zaman doğrudan API ile ilgilenecektir. MFC, çoğu durumda, çağıracaktır onu sizin için (WinMain, OLE Giriş noktalarının, adresindeki **AfxWndProc**, vb..). Bu yazma statik olarak özel bir bağlama tarafından herhangi bir bileşeni yapılır **WndProc**ve özel bir `WinMain` (veya `DllMain`) hangi Modül durumu geçerli bilir. Bu kod DLLMODUL bakarak görebilirsiniz. CPP veya APPMODUL. CPP MFC\SRC dizininde.  
  
 Modül durumu ayarlayın ve ardından onu geri ayarlanmadı istediğiniz nadir görülen bir durumdur. Çoğu "kendi modülü göndermek için" istediğiniz zaman, geçerli bir durum ve tamamladıktan sonra daha sonra "geri özgün içerik pop". Bu makro tarafından yapılır [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) ve özel sınıf **AFX_MAINTAIN_STATE**.  
  
 `CCmdTarget`Modül durumu geçiş desteklemek için özel özelliklere sahiptir. Özellikle, bir `CCmdTarget` olduğu kök sınıfı, giriş noktaları OLE Otomasyon ve OLE COM için kullanılır. Herhangi bir giriş noktası gibi sisteme kullanıma sunulan, bu giriş noktaları doğru Modül durumu ayarlamanız gerekir. Nasıl mu bir verilen `CCmdTarget` bilmeniz yanıt olan, "Bu oluşturulduğunda"geçerli"Modül durumu nedir hatırlıyor", sağlayacak şekilde ayarlayabilirsiniz "sonraki olduğunda değer olarak adlandırılan, geçerli modül durumunu hatırlanan" "doğru" Modül durumu olması gerekir. Sonuç olarak, Modül durumu, bir verilen `CCmdTarget` nesnesidir ilişkili olduğu nesne oluşturulan olduğunda geçerli Modül durumu. InProc sunucu yüklenirken, bir nesne oluşturma ve yöntemlerini çağıran basit bir örnek olur.  
  
1.  OLE tarafından yüklenen DLL kullanarak **LoadLibrary**.  
  
2. **RawDllMain** önce çağırılır. Modül durumu DLL için bilinen statik modülü durumuna ayarlar. Bu nedenle **RawDllMain** DLL'e statik olarak bağlanır.  
  
3.  Bizim nesneyle ilişkili üreteci oluşturucusu olarak adlandırılır. `COleObjectFactory`türetilmiş `CCmdTarget` ve sonuç olarak, hangi Modül durumu örneğinin başlatılmasından hatırlıyor. Bu önemlidir — nesneleri oluşturmak için üreteci sorulduğunda, bunu şimdi geçerli yapmak için hangi Modül durumu bilir.  
  
4. `DllGetClassObject`üreteci elde etmek için çağrılır. MFC bu modülü ile ilişkili sınıf Fabrika listesi arar ve döndürür.  
  
5. **COleObjectFactory::XClassFactory2::CreateInstance** olarak adlandırılır. Bu işlev Modül durumu nesnesi oluşturma ve onu döndürmeden önce adım 3'te geçerli bir modül durumuna ayarlar. (ne zaman geçerli bir `COleObjectFactory` örneğinin başlatılmasından). Bu içinde yapılır [METHOD_PROLOGUE](com-interface-entry-points.md).  
  
6.  Nesne oluşturulduğunda, çok olan bir `CCmdTarget` türetilmiş ve aynı şekilde `COleObjectFactory` hangi Modül durumu etkin hatırlanan şekilde bu yeni nesne yapar. Nesne geçiş yapmak için hangi Modül durumu bilir şimdi onu zaman çağrılır.  
  
7.  İstemci, alınan OLE COM nesnesi işlevi çağırır kendi `CoCreateInstance` çağırın. Nesne çağrıldığında kullanan `METHOD_PROLOGUE` Modül durumu tıpkı geçiş yapmak için `COleObjectFactory` yapar.  
  
 Gördüğünüz gibi oluşturuldukları sırada Modül durumu nesnesinden nesnesine yayılır. Modül durumu uygun şekilde ayarlanmış olması önemlidir. Ayarlanmazsa, DLL veya COM nesnesi kötü, çağırma veya kendi kaynaklarını bulamıyor olabilir ya da miserable diğer yollarla başarısız olabilir bir MFC uygulaması ile etkileşimde bulunabilir.  
  
 Belirli türdeki DLL'ler, özellikle "MFC uzantı" DLL'leri modülü durumda geçiş yapabilirim Not kendi **RawDllMain** (aslında, genellikle bile sahip olmayan bir **RawDllMain**). Bunları kullanan uygulamayı gerçekten var "gibi" davranmasını hedeflenen olmasıdır. Çalıştıran uygulama çok bir parçası olan ve bu uygulamanın genel durumunu değiştirmek için kendi amacınıza olur.  
  
 OLE denetimleri ve diğer DLL'ler çok farklıdır. Çağıran uygulamanın durumunu değiştir istemediğiniz; bunları çağırma uygulama MFC uygulaması bile olmayabilir ve bu nedenle olabilir değiştirmek için bir durum yok. Modül durumu geçiş bulunmuştur nedeni budur.  
  
 Bir iletişim kutusu, DLL içinde başlatır gibi DLL'den dışarı aktarılan işlevler için işlev başlangıcına aşağıdaki kodu eklemeniz gerekir:  
  
```  
AFX_MANAGE_STATE(AfxGetStaticModuleState())  
```  
  
 Bu döndürülen durumuyla geçerli modül durumunu değiştirir [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate) geçerli kapsam sonuna kadar.  
  
 DLL'leri kaynaklarında sorunları varsa gerçekleşeceği `AFX_MODULE_STATE` makrosu kullanılmaz. Varsayılan olarak, MFC kaynak şablonu yüklemek için ana uygulama kaynak tanıtıcısı kullanır. Bu şablon, aslında DLL'de depolanır. MFC'nin Modül durumu bilgilerini tarafından geçti değil, kök nedeni `AFX_MODULE_STATE` makrosu. Kaynak tanıtıcısı MFC'nin modülü durumundan kurtarıldı. Modül durumu geçiş değil, kullanılacak yanlış kaynağı tanıtıcısı neden olur.  
  
 `AFX_MODULE_STATE`DLL her işlevde yerleştirilmeye gerekmez. Örneğin, `InitInstance` uygulamayı olmadan MFC kodu tarafından çağrılan `AFX_MODULE_STATE` MFC modül durumu önce otomatik olarak kayar çünkü `InitInstance` ve ardından geri sonra anahtarları `InitInstance` döndürür. Aynı tüm ileti eşlemesi işleyicileri için geçerlidir. Normal MFC DLL'leri gerçekte herhangi ileti yönlendirme önce Modül durumu otomatik olarak geçer özel ana pencere yordamı vardır.  
  
## <a name="process-local-data"></a>İşlem yerel veriler  
 İşlem yerel veri, onu Win32 DLL modeli zorluk için olsaydı değil gibi harika sorun olmayacaktır. Win32 tüm DLL'ler bile birden çok uygulama tarafından yüklendiğinde genel verilerine paylaşır. Bu, çok burada her DLL DLL'e iliştirir her işlem, veri alanında ayrı bir kopyasını alır "gerçek" Win32 DLL veri modelinden farklıdır. Karmaşıklık eklemek için Win32 DLL'de yığında ayrılan veri aslında belirli (en az önceye sahipliği geçtikçe) işlemidir. Aşağıdaki veri ve kod göz önünde bulundurun:  
  
```  
static CString strGlobal; // at file scope  
 
__declspec(dllexport)   
void SetGlobalString(LPCTSTR lpsz)  
{  
    strGlobal = lpsz;  
}  
 
__declspec(dllexport)  
void GetGlobalString(LPCTSTR lpsz,
    size_t cb)  
{  
    StringCbCopy(lpsz,
    cb,
    strGlobal);

}  
```  
  
 Yukarıdaki kod DLL'de bulunuyorsa ve DLL iki işlemler tarafından A ve B (aslında, aynı uygulamanın iki örneğini olabilir) yüklenir ne olacağını düşünün. Bir çağrı `SetGlobalString("Hello from A")`. Sonuç olarak, bellek için ayrılan `CString` veri A. tut işlemi bağlamında aklınızda `CString` kendisi geneldir ve her iki A'ya görünür ve b Şimdi B çağırır `GetGlobalString(sz, sizeof(sz))`. B kümesi veri görmeye olacaktır. Win32 Win32 yaptığı gibi işlemleri arasındaki koruma sağladığından budur. İlk sorun olan; Çoğu durumda bir uygulama tarafından farklı bir uygulama sahibi olduğu kabul edildiği genel veri etkileyen etmesi değil.  
  
 Ek sorunlar vardır. Artık çıkar olduğunu düşünelim. A çıktığında, tarafından kullanılan bellek '`strGlobal`' dizesi sistemi için kullanılabilir hale — işlem A tarafından ayrılan tüm bellek işletim sistemi tarafından otomatik olarak diğer bir deyişle, serbest. Çünkü serbest değil `CString` yıkıcı çağrılma; henüz adlı kurmadı. Yalnızca serbest kendisi ayrılan uygulama Sahne bıraktığından. B çağrıldıklarında şimdi `GetGlobalString(sz, sizeof(sz))`, geçerli veri alamayabilirsiniz. Başka bir uygulama bu bellek başka bir şey için kullanmış olabilirsiniz.  
  
 Açıkça bir sorun var. MFC 3.x iş parçacığı yerel depolaması (TLS) adında bir teknik kullanılır. MFC 3.x, çağrılmaz olsa bile, Win32 altında gerçekten işlem yerel depolama dizini olarak davranan bir TLS dizin ayırma ve ardından bu TLS dizini göre tüm verileri başvuru. Bu iş parçacığı yerel veri Win32'depolamak için kullanılan TLS dizin benzer (aşağıda bu konu hakkında daha fazla bilgi için bkz.). Bu işlem başına en az iki TLS dizinlerini faydalanmak her MFC DLL neden oldu. Birçok OLE denetim DLL'leri (OCXs) yükleme için hesap, hızlı bir şekilde (yalnızca 64 kullanılabilir olduğundan) TLS dizinlerini dışında çalıştırın. Ayrıca, tüm bu verileri tek bir yapı tek bir yerde yerleştirmek MFC içeriyor. Çok Genişletilebilir değildi ve TLS dizinlerini kullanımına göre ideal değildi.  
  
 MFC 4.x sınıf şablonları, "kaydırma" işlem yerel olmalıdır veri kümesiyle bu adresleri. Örneğin, yukarıda açıklanan sorun yazarak düzeltilmesi:  
  
```  
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
  
 MFC bu iki adımda uygular. İlk olarak, Win32 en üstünde bir katmanı yok **Tls\***  API'leri (**TlsAlloc**, **TlsSetValue**, **TlsGetValue**, vb.), İşlem başına yalnızca iki TLS dizinleri kullanın, kaç tane DLL'leri olsun gerekir. İkinci, `CProcessLocal` şablonu bu verilere erişmek için sağlanır. İşleci geçersiz kılmalar -> olduğu ne yukarıda gördüğünüz sezgisel sözdizimi sağlar. Tarafından Sarmalanan tüm nesneleri `CProcessLocal` öğesinden türetilmelidir `CNoTrackObject`. `CNoTrackObject`alt düzey ayırıcısı sağlar (**LocalAlloc**/**LocalFree**) ve sanal yıkıcı sağlayacak şekilde işlem MFC işlem yerel nesneleri otomatik olarak yok edebilir sonlandırıldı. Ek temizleme gerekliyse, bu tür nesneleri özel yıkıcı olabilir. Derleyici katıştırılmış yok etmek için bir varsayılan yok Edicisi oluşturacak bu yana yukarıdaki örnekte, gerektirmeyen `CString` nesnesi.  
  
 Bu yaklaşımın ilginç başka avantajları vardır. Yalnızca tüm olan `CProcessLocal` otomatik olarak zarar nesnelerin gerekene kadar bunlar oluşturulur değil. `CProcessLocal::operator->`ilişkili nesne ilk zamana ve daha önce örneği oluşturulmaz. Yukarıdaki örnekte, anlamına '`strGlobal`' dize değil oluşturulan ilk kez kadar **SetGlobalString** veya **GetGlobalString** olarak adlandırılır. Bazı durumlarda, bu DLL başlatma süresini kısaltmanıza yardımcı olabilir.  
  
## <a name="thread-local-data"></a>İş parçacığı yerel veriler  
 Verileri için belirli bir iş parçacığı yerel benzer yerel verileri işlemek için iş parçacığı yerel veri kullanılır. Diğer bir deyişle, bu verilere eriştiğinde her iş parçacığı için verileri ayrı bir örneği gerekir. Bu sayıda kapsamlı eşitleme mekanizmaları yerine kullanılabilir. Veriler birden çok iş parçacığı tarafından paylaşılan gerekmez, bu tür mekanizmaları pahalı ve gereksiz olabilir. Biz sahip olduğunuzu varsayalım bir `CString` nesne (çok Yukarıdaki örnek benzer). Biz, iş parçacığı yerel ile kaydırma yapabilirsiniz bir `CThreadLocal` şablonu:  
  
```  
struct CMyThreadData : public CNoTrackObject  
{  
    CString strThread;  
};  
CThreadLocal<CMyThreadData> threadData;  
 
void MakeRandomString()  
{ *// a kind of card shuffle (not a great one)  
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
  
 Varsa `MakeRandomString` çağrıldı iki farklı iş parçacıklarından her "dizesini farklı şekillerde birbirleriyle engellemeden karışık". Bu olmadığından gerçekte bir `strThread` sadece bir genel örnek yerine iş parçacığı başına örnek.  
  
 Bir başvuru yakalamak için nasıl kullanıldığını unutmayın `CString` adres kez yerine bir kez döngü tekrarında. Döngü kodu ile yazılan `threadData->strThread` her yerde '`str`' kullanılır, ancak kodu yürütme çok daha yavaş olacaktır. Bu tür başvuruları Döngülerde oluştuğunda bir başvuru verileri önbelleğe almak en iyisidir.  
  
 `CThreadLocal` Sınıfı şablonu mekanizmalarının aynısını kullanır, `CProcessLocal` yapar ve aynı uygulama teknikler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

