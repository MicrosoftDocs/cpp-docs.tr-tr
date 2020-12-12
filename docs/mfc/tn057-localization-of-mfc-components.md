---
description: 'Hakkında daha fazla bilgi edinin: TN057: MFC bileşenlerini yerelleştirme'
title: 'TN057: MFC Bileşenlerini Yerelleştirme'
ms.date: 06/28/2018
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
ms.openlocfilehash: d4a331e74acd2b5b38ae059ea180a0a2148e3a0f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214812"
---
# <a name="tn057-localization-of-mfc-components"></a>TN057: MFC Bileşenlerini Yerelleştirme

> [!NOTE]
> Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

Bu notta, bir uygulama veya OLE denetimi ya da MFC kullanan bir DLL varsa, bileşeninizi yerelleştirmek için kullanabileceğiniz tasarımların ve yordamların bazıları açıklanmaktadır.

## <a name="overview"></a>Genel Bakış

MFC kullanan bir bileşeni yerelleştirilirken çözülmesi gereken aslında iki sorun vardır. İlk olarak, kendi kaynaklarınızı (dizeler, iletişim kutuları ve bileşeninizle ilgili diğer kaynaklar) yerelleştirmelisiniz. MFC kullanılarak oluşturulan çoğu bileşen ayrıca MFC tarafından tanımlanan çeşitli kaynakları içerir ve kullanır. Yerelleştirilmiş MFC kaynaklarını da sağlamanız gerekir. Neyse ki, birkaç dil MFC 'nin kendisi tarafından zaten sunulmaktadır.

Ayrıca, bileşeninizin hedef ortamında (Avrupa veya DBCS özellikli bir ortam) çalışmaya hazır olması gerekir. Çoğu bölüm için bu, uygulamanıza, yüksek bit kümesini doğru olarak vererek ve çift baytlık karakterlerle dizeleri işleyen verilerinize bağlıdır. MFC, bu ortamların her ikisi için varsayılan olarak etkindir, ancak yalnızca, kurulum sırasında yalnızca farklı kaynaklarla takılmış olan tek bir dünya çapındaki ikiliye sahip olmak mümkün olacaktır.

## <a name="localizing-your-components-resources"></a>Bileşeninizin kaynaklarını yerelleştirme

Uygulamanızı veya DLL 'nizi yerelleştirmeniz, kaynakları yalnızca hedef dille eşleşen kaynaklarla değiştirmeyi de kapsar. Kendi kaynaklarınız için bu oldukça basittir: kaynak düzenleyicisinde kaynakları düzenleyin ve uygulamanızı oluşturun. Kodunuz düzgün yazılmışsa, C++ kaynak kodunuza sabit kodlanmış bir dize veya metin olmaz; tüm yerelleştirme yalnızca kaynaklar değiştirilerek yapılabilir. Aslında, bir yerelleştirilmiş sürümü sağlamak için bir özgün kodun derlemesini dahil etmeyeceği gibi, bileşeninizi uygulayabilirsiniz. Bu daha karmaşıktır, ancak buna değer de budur ve MFC 'nin kendisi için seçilen mekanizmadır. Ayrıca, EXE veya DLL dosyasını kaynak düzenleyicisine yükleyip kaynakları doğrudan düzenleyerek uygulamayı yerelleştirmek mümkündür. Mümkün olsa da, uygulamanızın yeni bir sürümünü derlediğinizde her seferinde bu değişikliklerin yeniden uygulamaya ihtiyacı vardır.

Bunu önlemenin bir yolu, bazı durumlarda uydu DLL olarak da adlandırılan ayrı bir DLL 'de tüm kaynakları bulmaktır. Bu DLL daha sonra çalışma zamanında dinamik olarak yüklenir ve kaynaklar, tüm kodlarınızla ana modül yerine bu DLL 'den yüklenir. MFC bu yaklaşımı doğrudan destekler. MYAPP.EXE adlı bir uygulamayı düşünün; MYRES.DLL adlı bir DLL dosyasında bulunan tüm kaynakları olabilir. Uygulama, bu `InitInstance` DLL 'yi yüklemek için aşağıdaki işlemleri yapar ve MFC 'nin bu konumdan kaynak yüklemesine neden olur:

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

Bundan sonra, MFC myapp.exe yerine bu DLL 'den kaynak yükler. Ancak, tüm kaynakların bu DLL 'de mevcut olması gerekir; MFC, belirli bir kaynağı aramada uygulamanın örneğinde arama olmayacaktır. Bu teknik, normal MFC DLL 'Leri ve OLE denetimleri için de aynı şekilde geçerlidir. Kurulum programınız, kullanıcının hangi kaynak yerel ayarına benzediğine bağlı olarak MYRES.DLL uygun sürümünü kopyalayacağından.

Yalnızca bir DLL kaynağı oluşturmak oldukça kolaydır. Bir DLL projesi oluşturun, öğesini ekleyin. RC dosyasına ekleyin ve gerekli kaynakları ekleyin. Bu tekniği kullanmayan mevcut bir projeniz varsa, bu projedeki kaynakları kopyalayabilirsiniz. Kaynak dosyasını projeye ekledikten sonra, projeyi oluşturmaya neredeyse hazırsınızdır. Yapmanız gereken tek şey bağlayıcı seçeneklerini **/NOENTRY** içerecek şekilde ayarladı. Bu, bağlayıcıya DLL 'nin hiç giriş noktası olmadığını, hiçbir kod içermediğinden, hiçbir giriş noktası olmadığını söyler.

> [!NOTE]
> Visual C++ 4,0 ve üzeri sürümlerde kaynak Düzenleyicisi, başına birden çok dili destekler. RC dosyası. Bu, yerelleştirmenin tek bir projede yönetilmesini çok kolay hale getirir. Her dilin kaynakları, kaynak Düzenleyicisi tarafından oluşturulan Önişlemci yönergeleri tarafından denetlenir.

## <a name="using-the-provided-mfc-localized-resources"></a>Belirtilen MFC yerelleştirilmiş kaynaklarını kullanma

Oluşturduğunuz herhangi bir MFC uygulaması MFC 'den iki şeyi yeniden kullanır: kod ve kaynaklar. Diğer bir deyişle, MFC 'nin çeşitli hata iletileri, yerleşik iletişim kutuları ve MFC sınıfları tarafından kullanılan diğer kaynakları vardır. Uygulamanızı tamamen yerelleştirmek için, yalnızca uygulamanızın kaynaklarından değil, doğrudan MFC 'den gelen kaynakları da yerelleştirmeniz gerekir. MFC, hedeflediğiniz dil MFC 'nin zaten desteklediği dillerden biri ise, yalnızca bu yerelleştirilmiş kaynakları kullandığınızdan emin olmak için, otomatik olarak bir dizi farklı dil kaynak dosyası sağlar.

Bu yazma itibariyle MFC, Çince, Almanca, Ispanyolca, Fransızca, Italyanca, Japonca ve Korece 'yi destekler. Bu yerelleştirilmiş sürümleri içeren dosyalar MFC\INCLUDE\L. * ' dir (' L ' yerelleştirilmiş) dizinler. Almanya dosyaları, örneğin MFC\INCLUDE\L.exe DEU şeklindedir. Uygulamanızın MFC\INCLUDE dizininde yer alan dosyalar yerine bu RC dosyalarını kullanmasına neden olması için, `/IC:\PROGRAM FILES\MICROSOFT VISUAL STUDIO .NET 2003\VC7\MFC\INCLUDE\L.DEU` rc komut satırınızdaki bir ekleyin (Bu yalnızca bir örnektir; seçtiğiniz yerel ayarınızı ve Visual C++ yüklediğiniz dizini de değiştirmeniz gerekir).

Uygulamanız MFC ile statik olarak bağlanıyorsa yukarıdaki yönergeler çalışacaktır. Çoğu uygulama dinamik olarak bağlanır (çünkü bu, AppWizard varsayılandır). Bu senaryoda, yalnızca kod dinamik olarak bağlanmadığından, kaynaklardır. Sonuç olarak, uygulamanızda kaynaklarınızı yerelleştirebilirsiniz, ancak MFC Uygulama kaynakları hala MFC7x.DLL (veya sonraki bir sürüm) veya varsa MFC7xLOC.DLL yüklenir. Bunu iki farklı açıdan yaklaşımda bulabilirsiniz.

Daha karmaşık bir yaklaşım, yerelleştirilmiş MFC7xLOC.DLLs (örneğin, Almanca, Ispanyolca için MFC7xESP.DLL vb.) veya daha sonraki bir sürümü göndermek ve Kullanıcı uygulamanızı yüklediğinde sistem dizinine uygun MFC7xLOC.DLL yüklemektir. Bu, hem geliştirici hem de son kullanıcı için çok karmaşık olabilir ve bu nedenle önerilmez. Bu teknik ve uyarıları hakkında daha fazla bilgi için bkz. [Teknik Note 56](../mfc/tn056-installation-of-localized-mfc-components.md) .

En basit ve en güvenli yaklaşım, yerelleştirilmiş MFC kaynaklarını uygulamanıza veya DLL 'ye (bir tane kullanıyorsanız, uydu DLL 'sine) dahil etmek için kullanılır. Bu, MFC7xLOC.DLL düzgün şekilde yükleme sorunlarını önler. Bunu yapmak için, yukarıda verilen statik durum için aynı yönergeleri izleyerek (RC komut satırını yerelleştirilmiş kaynaklara işaret etmek için uygun şekilde ayarlama), ayrıca `/D_AFXDLL` AppWizard tarafından eklenen tanımla ' yı da kaldırmanız gerekir. `/D_AFXDLL`Tanımlandığında, AFXRES. H (ve diğer MFC RC dosyaları) gerçekte hiçbir kaynak tanımlamaz (Bunun yerine MFC DLL 'lerden çekilmeleri gerekir).

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
