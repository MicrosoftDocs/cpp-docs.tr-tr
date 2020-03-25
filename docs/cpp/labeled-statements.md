---
title: Etiketli Deyimler
ms.date: 11/04/2016
helpviewer_keywords:
- labeled statement
- statements, labeled
ms.assetid: 456a26d5-0fcc-4d1a-b71f-fa9ff3d73b91
ms.openlocfilehash: d971a0e9864aeada1db5f004ef70577512e78c76
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179698"
---
# <a name="labeled-statements"></a>Etiketli Deyimler

Etiketler program denetimini doğrudan belirtilen ifadeye aktarmak için kullanılır.

```
identifier :  statement
case constant-expression :  statement
default :  statement
```

Bir etiketin kapsamı, bildirildiği işlevin tamamıdır.

## <a name="remarks"></a>Açıklamalar

Üç etiketli deyim türü vardır. Tümü, bir etiket türünü deyimden ayırmak için iki nokta üst üste kullanır. Case ve default etiketleri Case deyimlerine özgüdür.

```cpp
#include <iostream>
using namespace std;

void test_label(int x) {

    if (x == 1){
        goto label1;
    }
    goto label2;

label1:
    cout << "in label1" << endl;
    return;

label2:
    cout << "in label2" << endl;
    return;
}

int main() {
    test_label(1);  // in label1
    test_label(2);  // in label2
}
```

**Goto ekstresi**

Kaynak programdaki bir *tanımlayıcı* etiketinin görünümü bir etiket bildirir. Yalnızca bir [goto](../cpp/goto-statement-cpp.md) deyimleri, denetimi bir *tanımlayıcı* etiketine aktarabilir. Aşağıdaki kod parçası, **goto** ifadesinin ve bir *tanımlayıcı* etiketinin kullanımını gösterir:

Etiket kendi başına görünemez, her zaman bir deyime bağlı olmalıdır. Tek başına bir etiket gerekiyorsa, etiketten sonra boş bir deyim koyun.

Etiket, işlev kapsamına sahiptir ve işlev içinde tekrar bildirilemez. Ancak aynı ad, farklı işlevlerde bir etiket olarak kullanılabilir.

```cpp
// labels_with_goto.cpp
// compile with: /EHsc
#include <iostream>
int main() {
   using namespace std;
   goto Test2;

   cout << "testing" << endl;

   Test2:
      cerr << "At Test2 label." << endl;
}

//Output: At Test2 label.
```

**Case ekstresi**

**Case** anahtar sözcüğünden sonra görünen Etiketler bir **Switch** ifadesinin dışında da görünmeyebilir. (Bu kısıtlama **varsayılan** anahtar sözcüğü için de geçerlidir.) Aşağıdaki kod parçası, **büyük/küçük harf** etiketlerinin doğru kullanımını gösterir:

```cpp
// Sample Microsoft Windows message processing loop.
switch( msg )
{
   case WM_TIMER:    // Process timer event.
      SetClassWord( hWnd, GCW_HICON, ahIcon[nIcon++] );
      ShowWindow( hWnd, SW_SHOWNA );
      nIcon %= 14;
      Yield();
      break;

   case WM_PAINT:
      memset( &ps, 0x00, sizeof(PAINTSTRUCT) );
      hDC = BeginPaint( hWnd, &ps );
      EndPaint( hWnd, &ps );
      break;

   default:
      // This choice is taken for all messages not specifically
      //  covered by a case statement.

      return DefWindowProc( hWnd, Message, wParam, lParam );
      break;
}
```

## <a name="labels-in-the-case-statement"></a>Case deyimindeki Etiketler

**Case** anahtar sözcüğünden sonra görünen Etiketler bir **Switch** ifadesinin dışında da görünmeyebilir. (Bu kısıtlama **varsayılan** anahtar sözcüğü için de geçerlidir.) Aşağıdaki kod parçası, **büyük/küçük harf** etiketlerinin doğru kullanımını gösterir:

```cpp
// Sample Microsoft Windows message processing loop.
switch( msg )
{
   case WM_TIMER:    // Process timer event.
      SetClassWord( hWnd, GCW_HICON, ahIcon[nIcon++] );
      ShowWindow( hWnd, SW_SHOWNA );
      nIcon %= 14;
      Yield();
      break;

   case WM_PAINT:
      // Obtain a handle to the device context.
      // BeginPaint will send WM_ERASEBKGND if appropriate.

      memset( &ps, 0x00, sizeof(PAINTSTRUCT) );
      hDC = BeginPaint( hWnd, &ps );

      // Inform Windows that painting is complete.

      EndPaint( hWnd, &ps );
      break;

   case WM_CLOSE:
      // Close this window and all child windows.

      KillTimer( hWnd, TIMER1 );
      DestroyWindow( hWnd );
      if ( hWnd == hWndMain )
         PostQuitMessage( 0 );  // Quit the application.
      break;

   default:
      // This choice is taken for all messages not specifically
      //  covered by a case statement.

      return DefWindowProc( hWnd, Message, wParam, lParam );
      break;
}
```

## <a name="labels-in-the-goto-statement"></a>Goto deyimindeki Etiketler

Kaynak programdaki bir *tanımlayıcı* etiketinin görünümü bir etiket bildirir. Yalnızca bir [goto](../cpp/goto-statement-cpp.md) deyimleri, denetimi bir *tanımlayıcı* etiketine aktarabilir. Aşağıdaki kod parçası, **goto** ifadesinin ve bir *tanımlayıcı* etiketinin kullanımını gösterir:

Etiket kendi başına görünemez, her zaman bir deyime bağlı olmalıdır. Tek başına bir etiket gerekiyorsa, etiketten sonra boş bir deyim koyun.

Etiket, işlev kapsamına sahiptir ve işlev içinde tekrar bildirilemez. Ancak aynı ad, farklı işlevlerde bir etiket olarak kullanılabilir.

```cpp
// labels_with_goto.cpp
// compile with: /EHsc
#include <iostream>
int main() {
   using namespace std;
   goto Test2;

   cout << "testing" << endl;

   Test2:
      cerr << "At Test2 label." << endl;
// At Test2 label.
}
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Deyimlerine Genel Bakış](../cpp/overview-of-cpp-statements.md)<br/>
[switch Deyimi (C++)](../cpp/switch-statement-cpp.md)
