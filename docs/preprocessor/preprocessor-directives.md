---
description: 'Daha fazla bilgi edinin: Önişlemci yönergeleri'
title: Ön işlemci yönergeleri
ms.date: 08/29/2019
helpviewer_keywords:
- directives, preprocessor
- preprocessor, directives
ms.assetid: e0fc4564-b6cf-4a36-bf51-6ccd7abd0a94
ms.openlocfilehash: 016021fb21961e71b56a734941d6c495cc6f6741
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240526"
---
# <a name="preprocessor-directives"></a>Ön işlemci yönergeleri

Ve gibi Önişlemci yönergeleri `#define` `#ifdef` genellikle kaynak programların farklı yürütme ortamlarında kolayca değiştirilmesini ve kolayca derlenmesi için kullanılır. Kaynak dosyadaki yönergeler, önişlemcinin belirli eylemleri geçirmesine söyler. Örneğin, Önişlemci metindeki belirteçleri değiştirebilir, diğer dosyaların içeriğini kaynak dosyasına ekleyebilir veya metnin parçalarını kaldırarak dosyanın bir kısmının derlemesini engelleyebilir. Ön işlemci satırları, makro genişletmesinden önce tanınır ve yürütülür. Bu nedenle, bir makro önişlemci komutu gibi görünen bir öğe halinde genişliyorsa, ön işlemci tarafından tanınmaz.

Önişlemci deyimleri, kaçış sıralarının desteklenmediği özel durum ile kaynak dosya deyimleriyle aynı karakter kümesini kullanır. Önişlemci deyimlerde kullanılan karakter kümesi yürütme karakter kümesiyle aynıdır. Önişlemci ayrıca negatif karakter değerlerini de tanır.

Önişlemci aşağıdaki yönergeleri tanır:

:::row:::
   :::column span="":::
      [`#define`](../preprocessor/hash-define-directive-c-cpp.md)\
      [`#elif`](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)\
      [`#else`](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)\
      [`#endif`](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)
   :::column-end:::
   :::column span="":::
      [`#error`](../preprocessor/hash-error-directive-c-cpp.md)\
      [`#if`](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)\
      [`#ifdef`](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)\
      [`#ifndef`](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)
   :::column-end:::
   :::column span="":::
      [`#import`](../preprocessor/hash-import-directive-cpp.md)\
      [`#include`](../preprocessor/hash-include-directive-c-cpp.md)\
      [`#line`](../preprocessor/hash-line-directive-c-cpp.md)
   :::column-end:::
   :::column span="":::
      [`#pragma`](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
      [`#undef`](../preprocessor/hash-undef-directive-c-cpp.md)\
      [`#using`](../preprocessor/hash-using-directive-cpp.md)
   :::column-end:::
:::row-end:::

Numara işareti ( `#` ), yönergeyi içeren satırdaki ilk boşluk olmayan karakter olmalıdır. Boşluk karakterleri, yönergenin sayı işareti ve ilk harfi arasında görünebilir. Bazı yönergeler bağımsız değişkenleri veya değerleri içerir. Bir yönergeyi takip eden herhangi bir metin (yönergenin parçası olan bir bağımsız değişken veya değer hariç) öncesinde tek satırlık açıklama sınırlayıcısı gelmelidir ( `//` ) veya açıklama sınırlayıcıları () içine alınmalıdır `/* */` . Önişlemci yönergelerini içeren satırlar, satır sonu işaretleyicisinden hemen önce bir ters eğik çizgiyle () devam edebilir `\` .

Önişlemci yönergeleri kaynak dosyanın herhangi bir yerinde görünebilir, ancak yalnızca kaynak dosyanın geri kalanı için geçerlidir.

## <a name="see-also"></a>Ayrıca bkz.

[Önişlemci işleçleri](../preprocessor/preprocessor-operators.md)\
[Önceden tanımlanmış makrolar](../preprocessor/predefined-macros.md)\
[c/c++ Önişlemci Başvurusu](../preprocessor/c-cpp-preprocessor-reference.md)
