---
title: Kaynak Tanımlayıcıları (simge) (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.symbol.identifiers
helpviewer_keywords:
- symbols [C++], resource identifiers
- symbols [C++], creating
- resource symbols
- symbols [C++], editing
- resource editors [C++], resource symbols
ms.assetid: 8fccc09a-0237-4a65-b9c4-57d60c59e324
ms.openlocfilehash: 0b19ff0d1c709616868d47c172ff4cf8c6931b82
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387883"
---
# <a name="resource-identifiers-symbols-c"></a>Kaynak Tanımlayıcıları (simge) (C++)

Bir semboldür iki bölümden oluşan bir kaynak tanımlayıcısı (ID) bir sembol değer (tamsayı), örneğin eşlenmiş bir sembol adını (metin dizesi):

```
IDC_EDITNAME = 5100
```

Sembol adları, en sık tanımlayıcı olarak da adlandırılır.

Semboller kaynaklara ve kullanıcı arabirimi nesneleri, kaynak kodunuzu hem de kendileriyle kaynak düzenleyicilerde çalışırken başvuran açıklayıcı bir yol sağlar. Görüntüleyebilir ve tek bir yerde kullanarak simgeleri düzenleme [kaynak sembolleri iletişim kutusu](../windows/viewing-resource-symbols.md).

Bu nedenle boyut ve karmaşıklık bakımından uygulamanız büyüdükçe, kaynakları ve semboller sayısı yapar. Semboller birkaç dosya dağılmış çok sayıda izlemek zor olabilir. **Kaynak sembolleri** iletişim kutusunda sembol Yönetim için merkezi bir aracı sunarak basitleştirir:

- [Semboller oluşturma](../windows/creating-new-symbols.md)

- [Semboller yönetme](../windows/changing-a-symbol-or-symbol-name-id.md)

- [Önceden tanımlanmış sembol kimlikleri görüntüleyin](../windows/predefined-symbol-ids.md)

Yeni bir kaynak veya kaynak nesnesi oluşturduğunuzda [kaynak düzenleyicileri](../windows/resource-editors.md) Örneğin, kaynak için varsayılan bir ad sağlamanız `IDC_RADIO1`ve bir değer atayın. Name değeri plus tanımı depolanan `Resource.h` dosya.

> [!NOTE]
> Kaynaklar veya kaynak nesneleri bir .rc dosyasından diğerine Kopyalamakta olduğunuz, Visual C++ aktarılan kaynak sembol değeri veya sembol adını ve sembol adlarını veya var olan dosyayı değerleri ile çakışmalarını önlemek için değeri değiştirilebilir.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)<br/>
[Kaynak Dosyalar](../windows/resource-files-visual-studio.md)<br/>
[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>