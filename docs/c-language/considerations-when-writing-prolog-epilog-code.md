---
description: 'Hakkında daha fazla bilgi: giriş/bitiş kodu yazarken dikkat edilmesi gerekenler'
title: Prolog-Epilog kodu yazarken dikkat edilmesi gerekenler
ms.date: 11/04/2016
helpviewer_keywords:
- layouts, stack frame
- stack frame layout
- __LOCAL_SIZE constant
- stack, stack frame layout
ms.assetid: 3b8addec-e809-48e4-b1d0-5bad133bd4b8
ms.openlocfilehash: 65416e915afa95a27658e2c7517da8f2868dfef9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293293"
---
# <a name="considerations-when-writing-prologepilog-code"></a>Giriş ve Bitiş Kodu Yazarken Dikkat Edilmesi Gerekenler

**Microsoft'a Özgü**

Kendi giriş ve bitiş kodu dizilerini yazmadan önce, yığın çerçevesinin nasıl düzenlendiğini anlamak önemlidir. Ayrıca, **__LOCAL_SIZE** önceden tanımlanmış sabiti nasıl kullanacağınızı öğrenmek de yararlı olur.

## <a name="cstack-frame-layout"></a><a name="_clang_c_stack_frame_layout"></a> CStack çerçeve düzeni

Bu örnekte, 32 bit işlevinde görünebilecek standart giriş kodu gösterilmektedir:

```
push     ebp                 ; Save ebp
mov      ebp, esp            ; Set stack frame pointer
sub      esp, localbytes     ; Allocate space for locals
push     <registers>         ; Save registers
```

`localbytes` değişkeni yerel değişkenler için yığında gereken bayt sayısını gösterir, `registers` değişkeni ise yığında kaydedilecek yazmaçların listesini gösteren bir yer tutucudur. Yazmaçları gönderdikten sonra, yığın üzerine başka bir uygun veri yerleştirebilirsiniz. Aşağıda ilgili sonuç kodu bulunmaktadır:

```
pop      <registers>         ; Restore registers
mov      esp, ebp            ; Restore stack pointer
pop      ebp                 ; Restore ebp
ret                          ; Return from function
```

Yığın her zaman aşağı doğru (yüksek bellek adreslerinden düşük olanlara) büyür. Taban işaretçisi (`ebp`) `ebp`'nin gönderilen değerine işaret eder. Yerel değişkenler alanı `ebp-2`'de başlar. Yerel değişkenlere erişmek için uygun değeri `ebp`'den çıkararak `ebp`'den bir uzaklık hesaplayın.

## <a name="the-__local_size-constant"></a><a name="_clang_the___local_size_constant"></a> __LOCAL_SIZE sabiti

Derleyici, işlev giriş kodunun satır içi assembler bloğunda kullanılmak üzere bir sabit, **__LOCAL_SIZE** sağlar. Bu sabit, özel giriş kodundaki yığın çerçevesinde yerel değişkenler için yer ayırmak üzere kullanılır.

Derleyici **__LOCAL_SIZE** değerini belirler. Değer, tüm kullanıcı tanımlı yerel değişkenlerin ve derleyici tarafından oluşturulan geçici değişkenlerin toplam bayt sayısıdır. **__LOCAL_SIZE** , yalnızca bir anında işlenen olarak kullanılabilir; bir ifadede kullanılamaz. Bu sabitin değerini değiştirmemeli veya yeniden tanımlamamalısınız. Örneğin:

```
mov      eax, __LOCAL_SIZE           ;Immediate operand--Okay
mov      eax, [ebp - __LOCAL_SIZE]   ;Error
```

Özel giriş ve bitiş dizileri içeren bir çıplak işlevin aşağıdaki örneği giriş dizisinde **__LOCAL_SIZE** kullanır:

```
__declspec ( naked ) func()
{
   int i;
   int j;

   __asm      /* prolog */
      {
      push   ebp
      mov      ebp, esp
      sub      esp, __LOCAL_SIZE
      }

   /* Function body */

   __asm      /* epilog */
      {
      mov      esp, ebp
      pop      ebp
      ret
      }
}
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Naked Işlevleri](../c-language/naked-functions.md)
