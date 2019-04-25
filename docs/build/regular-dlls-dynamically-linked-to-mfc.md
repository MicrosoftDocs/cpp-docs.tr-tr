---
title: Dinamik olarak MFC'ye bağlı normal MFC DLL'leri
ms.date: 11/04/2016
helpviewer_keywords:
- regular MFC DLLs [C++], dynamically linked to MFC
- AFX_MANAGE_STATE macro
- DLLs [C++], regular
- shared DLL versions [C++]
- dynamically linked DLLs [C++]
ms.assetid: b4f7ab92-8723-42a5-890e-214f4e29dcd0
ms.openlocfilehash: 3bfed5f75dab4c501708950fdb99f53c40ec142c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315007"
---
# <a name="regular-mfc-dlls-dynamically-linked-to-mfc"></a>Dinamik olarak MFC'ye bağlı normal MFC DLL'leri

MFC DLL dinamik olarak MFC'ye bağlı normal MFC dahili olarak kullandığı bir DLL'dir ve DLL'de dışa aktarılan işlevleri MFC veya MFC olmayan yürütülebilir dosyaları tarafından çağrılabilir. Adı açıklandığı gibi bu tür bir DLL, MFC (diğer adıyla MFC paylaşılan sürüm) dinamik bağlantı kitaplığı sürümü kullanılarak oluşturulur. İşlevleri, genellikle bir Normal MFC DLL standart C arabirimini kullanarak dışarı aktarılır.

Eklemelisiniz `AFX_MANAGE_STATE` MFC DLL için geçerli modül durumunu ayarlamak için dinamik olarak bağlanan normal MFC DLL'leri dışarı aktarılan işlevlerin başında makrosu. Bu, aşağıdaki kod satırını DLL'den dışarı aktarılan işlevlerin başına ekleyerek gerçekleştirilir:

```
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))
```

Dinamik olarak MFC'ye bağlı normal MFC DLL, aşağıdaki özelliklere sahiptir:

- Yeni bir Visual C++ 4.0 tarafından sunulan DLL türüdür budur.

- İstemci yürütülebilir, DLL'lerin (C, C++, Pascal, Visual Basic ve benzeri); kullanımını destekleyen herhangi bir dilde yazılabilir bir MFC uygulaması yok.

- Statik olarak bağlı normal MFC DLL'SİNİN, bu tür bir DLL, MFC DLL (paylaşılan MFC DLL olarak da bilinir) için dinamik olarak bağlıdır.

- Bu tür bir DLL bağlı MFC içeri aktarma kitaplığını MFC uzantısı dll veya MFC DLL kullanan uygulamalar için kullanılan hizmet örneğiyle aynı şöyledir: MFCxx(D).lib.

Dinamik olarak MFC'ye bağlı normal MFC DLL, aşağıdaki gereksinimlere sahiptir:

- Bu DLL'ler ile derlenmiş **_AFXDLL** tanımlanmış olduğu gibi MFC DLL için dinamik olarak bağlı yürütülebilir dosyadır. Ancak **_USRDLL** Ayrıca, statik olarak MFC'ye bağlı normal MFC DLL'SİNİN gibi tanımlanır.

- Bu tür bir DLL oluşturmalıdır bir `CWinApp`-türetilmiş sınıf.

- Bu tür bir DLL kullanan `DllMain` MFC tarafından sağlanan. Tüm özel DLL başlatma kodunda yerleştirin `InitInstance` üye işlevine ve sonlandırma kodu `ExitInstance` normal bir MFC uygulaması olduğu gibi.

Bu tür bir DLL, MFC dinamik bağlantı kitaplığı sürümünü kullandığından, bir DLL için açıkça geçerli Modül durumu ayarlamanız gerekir. Bunu yapmak için [AFX_MANAGE_STATE](../mfc/reference/extension-dll-macros.md#afx_manage_state) her işlevin başında makrosu DLL'den dışarı.

Normal MFC DLL'leri olmalıdır bir `CWinApp`-türetilmiş sınıf ve o uygulama sınıfın tek bir nesne gibi bir MFC uygulaması. Ancak, `CWinApp` DLL'nin nesne gibi bir ana ileti pompası yok `CWinApp` uygulamanın nesne.

Unutmayın `CWinApp::Run` mekanizması uygulamanın ana ileti göndericisi çünkü bir DLL için uygulanmaz. DLL'niz kalıcı olmayan iletişim veya kendi ana penceresi, uygulamanızın ana ileti pompası çağıran bir DLL dışarı yordam çağırmalıdır `CWinApp::PreTranslateMessage`.

Tüm DLL'ye özgü başlatmada yerleştirin `CWinApp::InitInstance` normal bir MFC uygulaması olduğu gibi üye işlevi. `CWinApp::ExitInstance` Üye işlevini, `CWinApp` sağlanan MFC'den türetilmiş sınıf olarak adlandırılan `DllMain` DLL kaldırılmadan önce işlev.

Uygulamanız ile paylaşılan dll MFCx0.dll ve Msvcr*0.dll (veya benzer dosyaları) dağıtmanız gerekir.

Dinamik olarak MFC'ye bağlı bir DLL de statik olarak MFC'ye bağlanamıyor. Uygulamaları bağlantı Normal MFC DLL'leri MFC'ye dinamik olarak, diğer DLL gibi bağlı.

Simgeler, genellikle bir Normal MFC DLL standart C arabirimini kullanarak dışarı aktarılır. Normal MFC DLL'den dışarı aktarılan bir işlevin bildirimi şuna benzer:

```
extern "C" __declspec(dllexport) MyExportedFunction( );
```

Normal MFC DLL'SİNİN içindeki tüm bellek ayırmaları DLL kalmalı; DLL geçirin veya çağıran yürütülebilir dosyadan aşağıdakilerden herhangi birini alıyorsunuz gerekir:

- MFC nesne işaretçileri

- MFC tarafından ayrılan bellek işaretçisi

Yukarıdakilerden herhangi biri yapmanız gerekiyorsa veya çağıran yürütülebilir dosyayı ve DLL arasında MFC'den türetilmiş nesneler geçirmek istiyorsanız, bir MFC uzantılı DLL oluşturmanız gerekir.

Verilerin bir kopyasını yaparsanız işaretçileri ayrılan bellek için C çalışma zamanı kitaplıkları tarafından bir uygulama ve DLL arasında geçirmek güvenlidir. Değil silmeli veya bu işaretçileri yeniden boyutlandırmak veya bellek kopyalayarak olmadan kullanın.

MFC'ye bağlanan normal bir MFC DLL dinamik olarak oluşturma, makro kullanmanız gereken [AFX_MANAGE_STATE](../mfc/reference/extension-dll-macros.md#afx_manage_state) MFC modül durumu doğru bir şekilde geçin. Bu, aşağıdaki kod satırını DLL'den dışarı aktarılan işlevlerin başına ekleyerek gerçekleştirilir:

```
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))
```

**AFX_MANAGE_STATE** statik olarak MFC'ye bağlanan normal MFC DLL'leri veya MFC uzantısı DLL'leri makrosu kullanılmamalıdır. Daha fazla bilgi için [MFC modüllerinin Durum verilerini yönetme](../mfc/managing-the-state-data-of-mfc-modules.md).

Örnek Normal MFC DLL'SİNİN yazma, derleme ve ilişkin bir örnek için bkz. [ile ilgili](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/DllScreenCap). Dinamik olarak MFC'ye bağlanan normal MFC DLL'leri hakkında daha fazla bilgi için soyut örneği için "Dönüştürme ile ilgili için dinamik olarak bağlantı ile MFC DLL" başlıklı bölüme bakın.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Normal MFC DLL'leri Başlat](run-time-library-behavior.md#initializing-regular-dlls)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [MFC'ye dinamik olarak bağlı normal MFC DLL'SİNİN modül durumları](module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)

- [MFC modüllerinin durum verisini yönetme](../mfc/managing-the-state-data-of-mfc-modules.md)

- [Normal MFC DLL'lerinde Veritabanı, OLE ve Yuva MFC uzantısı DLL'leri Kullanma](using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)

- [Bir DLL'in bir parçası MFC kullanma](../mfc/tn011-using-mfc-as-part-of-a-dll.md)

## <a name="see-also"></a>Ayrıca bkz.

[DLL Türleri](kinds-of-dlls.md)
