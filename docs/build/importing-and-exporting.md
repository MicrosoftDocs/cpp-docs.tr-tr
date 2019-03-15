---
title: İçeri ve Dışarı Aktarma
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], importing
- exporting DLLs [C++]
- importing DLLs [C++]
- DLLs [C++], exporting from
- __declspec(dllimport) keyword [C++]
ms.assetid: 7c44c2aa-2117-4cec-9615-a65bfd3f8f7b
ms.openlocfilehash: 882010cd28c291e9f49ca0f7dd9d646c70130184
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57815833"
---
# <a name="importing-and-exporting"></a>İçeri ve Dışarı Aktarma

Ortak semboller bir uygulamayı içeri aktarın veya İşlevler iki yöntemi kullanarak DLL'den dışarı aktarma:

- DLL'yi oluştururken bir modül tanım (.def) dosyası kullanma

- Anahtar kelimeler kullanmanız **__declspec(dllimport)** veya **__declspec(dllexport)** ana uygulamadaki bir işlev tanımı

## <a name="using-a-def-file"></a>.Def dosyası kullanma

Bir modül-tanımlama (.def) dosyası, bir DLL'nin çeşitli özniteliklerini tanımlayan bir veya daha fazla modül deyimi içeren bir metin dosyasıdır. Kullanmıyorsanız, **__declspec(dllimport)** veya **__declspec(dllexport)** DLL DLL işlevlerini dışa aktarmak için bir .def dosyası gerekir.

.Def dosyaları için kullanabileceğiniz [bir uygulamayı içeri aktarma](importing-using-def-files.md) veya [DLL'den dışarı aktarma](exporting-from-a-dll-using-def-files.md).

## <a name="using-declspec"></a>__Declspec kullanma

Visual C++ kullanan **__declspec(dllimport)** ve **__declspec(dllexport)** değiştirilecek **__export** daha önce Visual C++ 16-bit sürümlerinde kullanılan anahtar sözcüğü.

Kullanmanız gerekmez **__declspec(dllimport)** doğru ancak bunun yapılması derlemek kodunuzu daha iyi kod oluşturmak derleyicinin sağlar. Bir işlevin bir DLL içinde veya değil, normal bir DLL sınırı aşıldığında bir işlev çağrısında mevcut olabilecek bir yöneltme düzeyi atlayan bir kod oluşturmak derleyicinin sağlayan mevcut olup olmadığını belirleyebilirsiniz çünkü daha iyi kod oluşturmak derleyicinin kuramıyor. Ancak, kullanmalısınız **__declspec(dllimport)** bir DLL içinde kullanılan değişkenler içeri aktarmak için.

Uygun .def dosyası dışarı AKTARMALARI bölümüyle **__declspec(dllexport)** gerekli değildir. **__declspec(dllexport)** işlevler .def dosyası kullanmadan bir .exe veya .dll dosyasından dışarı aktarmak için kolay bir yol sağlamak üzere eklendi.

Win32 taşınabilir yürütülebilir dosya biçimi, içeri aktarmalar düzeltmek için değiştirilmesi gereken sayfa sayısını en aza indirmek için tasarlanmıştır. Bunu yapmak için her program için tüm içe aktarma adreslerini içeri aktarma adres tablosu olarak adlandırılan tek bir yerde yerleştirir. Bu, yalnızca bir veya iki sayfa aktarmalara erişirken değiştirmesini sağlar.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Bir uygulamaya içeri aktarma](importing-into-an-application-using-declspec-dllimport.md)

- [DLL'den dışarı aktarma](exporting-from-a-dll.md)

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++'ta DLL'ler](dlls-in-visual-cpp.md)
