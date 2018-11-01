---
title: 'Semboller: Kaynak Tanımlayıcıları (C++)'
ms.date: 11/04/2016
f1_keywords:
- vc.editors.symbol.identifiers
helpviewer_keywords:
- symbols [C++], resource identifiers
- symbols [C++], creating
- resource symbols
- symbols [C++], editing
- resource editors [C++], resource symbols
ms.assetid: 8fccc09a-0237-4a65-b9c4-57d60c59e324
ms.openlocfilehash: abe6297d74df4941328d3e606fb3b0f646d36265
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50530006"
---
# <a name="symbols-resource-identifiers-c"></a>Semboller: Kaynak Tanımlayıcıları (C++)

İki bölümden oluşan bir kaynak tanımlayıcısı (ID) bir semboldür: tamsayı değerine (sembol değeri) eşlenmiş bir metin dizesi (sembol adı). Örneğin:

```
IDC_EDITNAME = 5100
```

Sembol adları, en sık tanımlayıcı olarak da adlandırılır.

Semboller kaynaklara ve kullanıcı arabirimi nesneleri, kaynak kodunuzu hem de kendileriyle kaynak düzenleyicilerde çalışırken başvuran açıklayıcı bir yol sağlar. Görüntüleyebilir ve tek bir yerde kullanarak simgeleri düzenleme [kaynak sembolleri iletişim kutusu](../windows/viewing-resource-symbols.md).

Yeni bir kaynak veya kaynak nesnesi oluşturduğunuzda [kaynak düzenleyicileri](../windows/resource-editors.md) Örneğin, kaynak için varsayılan bir ad sağlamanız `IDC_RADIO1`ve bir değer atayın. Name değeri plus tanımını Resource.h dosyasında depolanır.

> [!NOTE]
> Kaynaklar veya kaynak nesneleri bir .rc dosyasından diğerine Kopyalamakta olduğunuz, Visual C++ aktarılan kaynak sembol değeri veya sembol adını ve sembol adlarını veya var olan dosyayı değerleri ile çakışmalarını önlemek için değeri değiştirilebilir.

Bu nedenle boyut ve karmaşıklık bakımından uygulamanız büyüdükçe, kaynakları ve semboller sayısı yapar. Semboller birkaç dosya dağılmış çok sayıda izlemek zor olabilir. [Kaynak sembolleri iletişim kutusu](../windows/resource-symbols-dialog-box.md) için merkezi bir aracı sunarak sembol yönetimini kolaylaştırır:

- [Kaynak sembolleri görüntüleme](../windows/viewing-resource-symbols.md)

- [Yeni semboller oluşturma](../windows/creating-new-symbols.md)

- [Atanmamış sembolleri değiştirme](../windows/changing-unassigned-symbols.md)

- [Atanmamış sembolleri silme](../windows/deleting-unassigned-symbols.md)

- [Belirli bir sembol için kaynak Düzenleyicisini açma](../windows/opening-the-resource-editor-for-a-given-symbol.md)

- [Sembolü veya sembol adını (ID) değiştirme](../windows/changing-a-symbol-or-symbol-name-id.md)

- [Sembolün sayısal değerini değiştirme](../windows/changing-a-symbol-s-numeric-value.md)

- [Sembol başlık dosyalarının adlarını değiştirme](../windows/changing-the-names-of-symbol-header-files.md)

- [İçerir (salt okunur) paylaşılan veya hesaplanan sembolleri ekleme](../windows/including-shared-read-only-or-calculated-symbols.md)

- [Önceden tanımlanmış sembol kimlikleri görüntüleyin](../windows/predefined-symbol-ids.md)

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Nasıl yapılır: Sembolleri Kaynaklarda Arama](../windows/how-to-search-for-symbols-in-resources.md)<br/>
[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
[Kaynak dosyaları](../windows/resource-files-visual-studio.md)