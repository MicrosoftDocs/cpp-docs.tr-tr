---
title: GetProcAddress
ms.date: 11/04/2016
f1_keywords:
- GetProcAddress
helpviewer_keywords:
- DLLs [C++], GetProcAddress
- ordinal exports [C++]
- GetProcAddress method
ms.assetid: 48d14ae0-47ea-4c5d-96b1-2c158f1a26af
ms.openlocfilehash: 5ee985da29e38bfb262c72315a57c0b588b2e82e
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810178"
---
# <a name="getprocaddress"></a>GetProcAddress

Açıkça bir DLL'ye işlemleri [GetProcAddress](/windows/desktop/api/libloaderapi/nf-libloaderapi-getprocaddress) DLL'de dışa aktarılan bir işlevin adresini almak için. DLL işlevini çağırmak için döndürülen işlev işaretçisini kullanırsınız. **GetProcAddress** DLL modül tanıtıcısını parametreler olarak alan (tarafından döndürülen **LoadLibrary**, `AfxLoadLibrary`, veya **GetModuleHandle**) ve ya da istediğiniz işlevin adını alır çağrı veya işlevin dışa aktarma sıra sayısı.

DLL işlevini bir işaretçiyle çağırdığınızdan emin ve derleme zamanı türü denetimi yoktur çünkü böylece etmez yığında ayrılan belleğin çağırdığınızdan ve erişim ihlaline neden işlev parametrelerinin doğru olduğundan emin olun. Tür güvenliğini sağlamaya yardımcı olacak bir yol dışarı aktarılan işlevlerin işlev prototipleri Ara ve işlev işaretçilerine ilişkin eşleşen tür tanımları oluşturmaktır. Örneğin:

```
typedef UINT (CALLBACK* LPFNDLLFUNC1)(DWORD,UINT);
...

HINSTANCE hDLL;               // Handle to DLL
LPFNDLLFUNC1 lpfnDllFunc1;    // Function pointer
DWORD dwParam1;
UINT  uParam2, uReturnVal;

hDLL = LoadLibrary("MyDLL");
if (hDLL != NULL)
{
   lpfnDllFunc1 = (LPFNDLLFUNC1)GetProcAddress(hDLL,
                                           "DLLFunc1");
   if (!lpfnDllFunc1)
   {
      // handle the error
      FreeLibrary(hDLL);
      return SOME_ERROR_CODE;
   }
   else
   {
      // call the function
      uReturnVal = lpfnDllFunc1(dwParam1, uParam2);
   }
}
```

Belirttiğiniz çağrılırken istediğiniz işlevi nasıl **GetProcAddress** DLL nasıl oluşturulmuş bağlıdır.

Bağlandığınız DLL modül tanımı (.def) dosyasıyla oluşturulursa ve sıra sayıları işlevlerle listelenirse yalnızca dışarı aktarma sırası edinebilirsiniz **dışarı AKTARMALARI** DLL'nin .def dosyası bölümünü. Çağırma **GetProcAddress** dışa işlev adının bir sıra DLL birçok dışa aktarılan işleve sahipse dışa aktarma sıra sayıları DLL içine Dizinler tabloyu dışarı aktarma gibi gördükleri için biraz daha hızlıdır. Bir dışarı aktarma sırası ile **GetProcAddress** işlevi DLL'nin dışarı aktarma tablosundaki işlev adlarını belirtilen adla karşılaştırarak değil doğrudan bulabilir. Ancak, çağırmalıdır **GetProcAddress** yalnızca .def dosyasında dışa aktarılan işlevlere sıra sayıları atama denetiminiz varsa dışarı aktarma sırası ile.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Bir yürütülebilir dosyayı DLL’ye bağlama](linking-an-executable-to-a-dll.md#linking-implicitly)

- [Bir yürütülebilir dosyayı DLL’ye bağlama](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [LoadLibrary ve AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)

- [FreeLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-freelibrary)

- [DEF Dosyaları Kullanarak DLL'den Dışarı Aktarma](exporting-from-a-dll-using-def-files.md)

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++'ta DLL'ler](dlls-in-visual-cpp.md)
