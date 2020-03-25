---
title: Kaynak tanımlayıcıları (semboller) (C++)
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
ms.openlocfilehash: ba0958e455557660ef704f1c2fa570d46307082f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214402"
---
# <a name="resource-identifiers-symbols-c"></a>Kaynak tanımlayıcıları (semboller) (C++)

Sembol, bir sembol değeriyle (tamsayı) eşlenmiş bir sembol adı (metin dizesi) olan iki bölümden oluşan bir kaynak tanımlayıcısıdır (ID). Örneğin:

```
IDC_EDITNAME = 5100
```

Sembol adları genellikle tanımlayıcılar olarak adlandırılır.

Semboller, kaynaklar ve Kullanıcı arabirimi nesnelerine, hem kaynak kodunuzda hem de kaynak düzenleyicilerinde çalışırken bunlarla ilgili açıklayıcı bir yol sağlar. Sembolleri, [kaynak sembolleri iletişim kutusunu](../windows/viewing-resource-symbols.md)kullanarak bir uygun yerde görüntüleyebilir ve yönetebilirsiniz.

Uygulamanız boyut ve gelişmiş algoritmaların mümkündür büyüdükçe, kaynak ve sembol sayısını de vardır. Birçok dosya genelinde dağılmış çok sayıda sembol izlemek zor olabilir. **Kaynak sembolleri** iletişim kutusu, ' de kullanabileceğiniz bir merkezi araç sunarak sembol yönetimini basitleştirir:

- [Sembol oluştur](../windows/creating-new-symbols.md)

- [Sembolleri Yönet](../windows/changing-a-symbol-or-symbol-name-id.md)

- [Önceden tanımlanmış sembol kimliklerini görüntüle](../windows/predefined-symbol-ids.md)

Yeni bir kaynak veya kaynak nesnesi oluşturduğunuzda, [kaynak düzenleyicileri](../windows/resource-editors.md) kaynak için varsayılan bir ad sağlar, örneğin, `IDC_RADIO1`ve buna bir değer atar. Ad ve değer tanımı `Resource.h` dosyasında depolanır.

> [!NOTE]
> Bir. RC dosyasındaki kaynakları veya kaynak nesneleri diğerine kopyalarken, Visual C++ , var olan dosyadaki sembol adlarıyla veya değerlerle çakışmayı önlemek için, aktarılan kaynağın sembol değerini veya sembol adını ve değerini değiştirebilir.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)<br/>
[Kaynak Dosyalar](../windows/resource-files-visual-studio.md)<br/>
[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
