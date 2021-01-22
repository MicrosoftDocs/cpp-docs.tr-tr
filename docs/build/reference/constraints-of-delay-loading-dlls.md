---
description: 'Daha fazla bilgi edinin: DLL yükleme gecikmesi kısıtlamaları'
title: DLL'leri yüklemede gecikme kısıtlamaları
ms.date: 01/19/2021
helpviewer_keywords:
- constraints [C++], delayed loading of DLLs
- delayed loading of DLLs, constraints
- DLLs [C++], constraints
ms.openlocfilehash: 0bc29695aa48fea08a0126d4b814329656a5d3bf
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/21/2021
ms.locfileid: "98666985"
---
# <a name="constraints-of-delay-loading-dlls"></a>DLL'leri yüklemede gecikme kısıtlamaları

DLL içeri aktarımlarının gecikme yüklemesinde çeşitli kısıtlamalar vardır.

- Verilerin içeri aktarmaları desteklenmez. Geçici bir çözüm, `LoadLibrary` (veya `GetModuleHandle` gecikme Yükleme Yardımcısı 'nın dll 'yi yükledikten sonra kullanarak) verileri doğrudan içeri aktarmayı açıkça işleymaktır `GetProcAddress` .

- Yükleme gecikmesi *`Kernel32.dll`* desteklenmez. Bu DLL 'nin çalışması gecikmeli yük Yardımcısı yordamları için yüklenmelidir.

- İletilen giriş noktalarının [bağlanması](binding-imports.md) desteklenmez.

- Bir işlem, bir DLL gecikmeli yüklenmişse, başlatma sırasında yüklenmeden farklı davranış gösterebilir. Gecikmeli yüklenen DLL 'nin giriş noktasında gerçekleşen işlem başına başlatmalar varsa bu durum görülebilir. Diğer durumlarda, kullanılarak belirtilen statik TLS (iş parçacığı yerel depolaması), [`__declspec(thread)`](../../cpp/thread.md) Ile dll ile yüklendiğinde işlenmez `LoadLibrary` . ,,, Ve kullanan dinamik TLS, `TlsAlloc` `TlsFree` `TlsGetValue` `TlsSetValue` statik veya Gecikmeli yüklenen dll 'lerde kullanılmaya devam etmektedir.

- Her bir işlevin ilk çağrısından sonra içeri aktarılan işlevlere statik genel işlev işaretçilerini yeniden başlatın. Bu gereklidir çünkü bir işlev işaretçisinin ilk kullanımı, yüklü işlevi değil dönüştürücü için işaret ediyor.

- Şu anda, normal içeri aktarma mekanizmasını kullanırken bir DLL 'den yalnızca belirli yordamları yüklemeyi geciktirmenin bir yolu yoktur.

- Özel çağırma kuralları (x86 mimarilerinde koşul kodlarını kullanma gibi) desteklenmez. Ayrıca, kayan nokta kayıtları herhangi bir platformda kaydedilmez. Özel yardımcı yordamınız veya kanca yordamlarınız kayan nokta türlerini kullanıyorsa, çağırma kurallarını kayan nokta parametreleriyle kaydet kullanan makinelerde tam kayan nokta durumunu kaydedip geri yüklemesi gerekir. Özellikle, yardım işlevindeki bir sayısal veri işlemcisi (NDP) yığınında kayan nokta parametreleri alan CRT işlevleri çağırırsanız, CRT DLL 'nin Gecikmeli yükleme konusunda dikkatli olun.

## <a name="see-also"></a>Ayrıca bkz.

[Gecikmeli yüklenen dll 'Ler için bağlayıcı desteği](linker-support-for-delay-loaded-dlls.md)\
[`LoadLibrary` çalışmayacaktır](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryw)\
[`GetModuleHandle` çalışmayacaktır](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulehandlew)\
[`GetProcAddress` çalışmayacaktır](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress)\
[`TlsAlloc` çalışmayacaktır](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc)\
[`TlsFree` çalışmayacaktır](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsfree)\
[`TlsGetValue` çalışmayacaktır](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsgetvalue)\
[`TlsSetValue` işlevi](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlssetvalue)
