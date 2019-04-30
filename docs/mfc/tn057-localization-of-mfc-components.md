---
title: 'TN057: MFC bileşenlerini yerelleştirme'
ms.date: 06/28/2018
f1_keywords:
- vc.mfc.components
helpviewer_keywords:
- components [MFC], localizing
- TN057
- resources [MFC], localization
- localization [MFC], MFC resources
- localization [MFC], MFC components
- MFC DLLs [MFC], localizing
- DLLs [MFC], localizing MFC
- localization [MFC], resources
ms.assetid: 5376d329-bd45-41bd-97f5-3d895a9a0af5
ms.openlocfilehash: 812c2d29c42b523d7b88b03741dc20f08ee70f44
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399635"
---
# <a name="tn057-localization-of-mfc-components"></a>TN057: MFC bileşenlerini yerelleştirme

> [!NOTE]
> Aşağıdaki Teknik Not çevrimiçi belgelere ilk eklenmiştir beri güncelleştirilmemiş. Eski veya yanlış sonuç olarak, bazı yordamlar ve konular olabilir. En son bilgiler için bu konuyu çevrimiçi belge dizininde arama önerilir.

Bu Not tasarımları ve bir uygulama ya da bir OLE denetimi, bileşeninizin yerelleştirmek için kullanabileceğiniz yordamları veya MFC kullanan bir DLL bazılarını açıklar.

## <a name="overview"></a>Genel Bakış

Bir sorun kalmadığını gerçekten ne zaman çözmek için iki MFC kullanan bileşen yerelleştirme. İlk olarak, kendi kaynaklarını yerelleştirmesine gerekir — dizeleri, iletişim kutuları ve bileşeninize özgü diğer kaynaklar. MFC ayrıca kullanılarak oluşturulan çoğu bileşenleri içerir ve MFC tarafından tanımlanan kaynakları kullanma. Yerelleştirilmiş MFC kaynağı da sağlamanız gerekir. Neyse ki, çeşitli diller, MFC tarafından zaten sağlanır.

Ayrıca, bileşeninizin, hedef ortamda (Avrupa veya DBCS özellikli ortamı) çalıştırmak için hazırlıklı olmalıdır. Çoğunlukla, bu uygulamanızın yüksek bit kümesiyle karakterleri doğru bir şekilde değerlendirmek ve çift baytlık karakterler içeren dizeleri işleme bağlıdır. Kurulum sırasında prize takılı yalnızca farklı kaynaklar ile tüm platformlarda kullanılan tek bir dünya çapında ikili olması mümkündür, MFC, varsayılan olarak, hem de bu ortamların etkindir.

## <a name="localizing-your-components-resources"></a>Bileşeninizin kaynakları yerelleştirme

Uygulamanızı veya DLL yerelleştirme kaynakları ile eşleşen hedef dil kaynakları yalnızca değiştirme içermelidir. Kendi kaynakları için bu oldukça basittir: Kaynak Düzenleyicisi kaynakları düzenlemek ve uygulamanızı. Kodunuzu hiçbir dizeler veya yerelleştirmek için sabit kodlanmış C++ kaynak kodunuza - istediğiniz metin düzgün bir şekilde yazılmış tüm yerelleştirme kaynaklarını değiştirerek gerçekleştirilebilir. Aslında, tüm yerelleştirilmiş bir sürümünü sağlama bile özgün koda yapısı içermeyen, bileşeninizin uygulayabilirsiniz. Bu daha karmaşıktır, ancak iyi etkiliyorsa ve MFC için seçilen mekanizmadır. Kaynak Düzenleyicisi'ne EXE veya DLL dosyasını yüklerken ve kaynakları doğrudan düzenleyerek bir uygulamayı yerelleştirme da mümkündür. Olası sırasında uygulamanızın yeni bir sürümünü oluşturmak her zaman yeniden bu değişiklikleri gerektirir.

Bunu önlemek için bir yol, bir uydu DLL olarak da adlandırılır ayrı bir DLL içinde tüm kaynaklar bulmaktır. Bu DLL ardından dinamik olarak çalışma zamanında yüklendiği ve kaynakları yerine bu DLL ile tüm kodunuzu ana modülünden gelen yüklenir. MFC, doğrudan bu yaklaşım da destekler. MYAPP adlı bir uygulamayı düşünün. EXE; MYRES adlı bir DLL içinde yer alan, kaynaklarının tümünü olabilir. DLL. İçinde uygulamanın `InitInstance` bu DLL'yi ve MFC kaynakları o konumdan yüklemek aşağıdaki gerçekleştirmelisiniz:

```cpp
CMyApp::InitInstance()
{
    // one of the first things in the init code
    HINSTANCE hInst = LoadLibrary("myres.dll");

    if (hInst != NULL)
        AfxSetResourceHandle(hInst);

    // other initialization code would follow
    // ...
}
```

Daha sonra MFC kaynakları myapp.exe yerine bu DLL'ndan yüklenir. Tüm kaynaklar, ancak bu DLL içinde mevcut olması gerekir; MFC uygulamanın örnek saldırılar belirli bir kaynağın aramaz. Bu teknik OLE denetimlerin yanı sıra eşit derecede iyi kadar Normal MFC DLL'leri için geçerlidir. Kurulum programınıza uygun sürümünü MYRES kopyalanır. DLL hangi kaynak yerel ayara olarak kullanıcı istersiniz.

Bir kaynak oluşturmak oldukça kolaydır yalnızca DLL. Bir DLL projesi oluşturma, ekleme. RC için dosya ve gerekli kaynakları ekleyin. Bu teknik kullanmayan var olan bir proje varsa, bu projeden kaynakları kopyalayabilirsiniz. Kaynak dosyasını projeye ekledikten sonra projeyi derlemek neredeyse hazırsınız demektir. Yapmanız gereken tek şey bağlayıcı seçenekleri içerecek şekilde ayarlandıysa **/NOENTRY**. Bu DLL giriş noktası yok - olduğunu söyler kod olduğundan, hiç giriş noktası yok.

> [!NOTE]
> Kaynak Düzenleyicisi Visual C++ 4.0 ve üzeri başına birden çok dili destekler. RC dosyası. Bu, tek bir projede yerelleştirme Yönetimi çok kolay zorlaştırabilir. Her dil için kaynaklar, önişlemci yönergeleri kaynak düzenleyici tarafından oluşturulan tarafından denetlenir.

## <a name="using-the-provided-mfc-localized-resources"></a>Yerelleştirilmiş kaynakları sağlanan MFC kullanma

Oluşturduğunuz herhangi bir MFC uygulaması iki şey MFC'den yeniden kullanır: kod ve kaynaklar. Diğer bir deyişle, MFC, çeşitli hata iletileri, yerleşik iletişim kutuları ve MFC sınıfları tarafından kullanılan diğer kaynaklar vardır. Uygulamanızı tamamen yerelleştirmek için yalnızca uygulamanızın kaynakları, aynı zamanda doğrudan MFC'den gelen kaynakları yerelleştirmek gerekir. MFC birkaç farklı dil kaynak dosyaları hedeflediğiniz dil MFC zaten desteklediği dillerden biriyle ise, bu yerelleştirilmiş kaynakların kullanmasını sağlamak yeterlidir, böylece otomatik olarak sağlar.

Bu makalenin yazıldığı tarih itibarıyla, Çince, Almanca, İspanyolca, Fransızca, İtalyanca, Japonca ve Korece MFC destekler. Bu yerelleştirilmiş sürümlerini içeren içinde MFC\INCLUDE\L.* dosyalardır (yerelleştirilmiş temsil 'L') dizinleri. Alman MFC\INCLUDE\L.DEU örneğin dosyalarıdır. Neden MFC\INCLUDE içinde bulunan dosyalar yerine bu RC dosyaları kullanmak uygulamanızı ekleyin bir `/IC:\PROGRAM FILES\MICROSOFT VISUAL STUDIO .NET 2003\VC7\MFC\INCLUDE\L.DEU` RC, komut satırı için (Bu yalnızca bir örnektir; Visual C yüklediğiniz dizine yanı sıra seçim bölgeniz yerine gerekir ++).

Uygulamanız MFC ile statik olarak bağlanıyorsa yukarıdaki yönergeler çalışır. Çoğu uygulama, dinamik olarak (Bu AppWizard varsayılan olduğundan) bağlayın. Bu senaryoda, yalnızca dinamik olarak kodudur bağlı - böylece kaynak olarak kullanılabilir. Sonuç olarak, uygulamanızda kaynaklarınızı yerelleştirebilirsiniz ancak varsa MFC uygulaması kaynakları hala MFC7x.DLL (veya sonraki bir sürümü) veya MFC7xLOC.DLL yüklenir. Bu iki farklı açıları yaklaşımını.

Daha karmaşık bir yaklaşım sevk yerelleştirilmiş MFC7xLOC.DLLs birini (örneğin, Almanca için MFC7xDEU, MFC7xESP.DLL İspanyolca, vb.) veya sonraki bir sürümünü ve kullanıcı uygulamanızı yüklendiğinde uygun MFC7xLOC.DLL sistem dizine yükleyin. Bu, geliştirici ve son kullanıcı için çok karmaşık olabilir ve bu nedenle önerilmez. Bkz: [Teknik Not 56](../mfc/tn056-installation-of-localized-mfc-components.md) Bu teknik ve kendi uyarılar hakkında daha fazla bilgi için.

Basit ve güvenli bir yaklaşım, uygulamanızın veya kendisine (veya kendi uydu DLL birini kullanmanız durumunda) bir DLL içinde yerelleştirilmiş MFC kaynakları dahil etmektir. Bu MFC7xLOC.DLL düzgün yükleme sorunları önler. Aynı yönergeleri (düzgün yerelleştirilmiş kaynakları işaret edecek şekilde RC komut satırı ayarlayarak yukarıda) verilen statik çalışması için bunu yapmak için ayrıca kaldırmalısınız dışındaki `/D_AFXDLL` tanımlayan AppWizard tarafından eklendi. Zaman `/D_AFXDLL` olan AFXRES tanımlı. (Bunlar MFC DLL'leri yerine çekilir çünkü) H (ve diğer MFC RC dosyaları) gerçekte herhangi bir kaynağa tanımlamaz.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
