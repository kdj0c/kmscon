# SPDX-FileCopyrightText: 2022 Aetf <aetf@unlimited-code.works>
#
# SPDX-License-Identifier: MIT

foreach name, deps : {
  'output': [uterm_deps],
  'vt': [uterm_deps],
  'input': [uterm_deps],
  'key': [],
}
  deps += [
    shl_deps,
    conf_deps,
    xkbcommon_deps,
  ]
  test_name = f'test_@name@'
  exe = executable(test_name, f'@test_name@.c',
    dependencies: deps,
  )
endforeach

test_shl = executable('test_shl', 'test_shl.c',
  dependencies: [shl_deps, check_deps],
)
test('test_shl', test_shl,
  protocol: 'tap',
  env: {'CK_TAP_LOG_FILE_NAME': '-', 'CK_VERBOSITY': 'silent'},
)
