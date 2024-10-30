<DayPickerRangeController            
      onDatesChange={(newDate) => setDate1(newDate)}
      focused={true}
      onFocusChange={({focused}) => focused}
      numberOfMonths={1}
      renderMonthElement={({ month, onMonthSelect, onYearSelect }) => (
        <div style={{ display: 'flex', justifyContent: 'center' }}>
          <div>
            <select
              value={month.month()}
              onChange={(e) => { onMonthSelect(month, e.target.value); }}
            >
              {moment.months().map((label, value) => (
                <option value={value}>{label}</option>
              ))}
            </select>
          </div>
          <div>
            <select
              value={month.year()}
              onChange={(e) => { onYearSelect(month, e.target.value); }}
            >
              <option value={moment().year() - 2}>Last year</option>
              <option value={moment().year() - 1}>Last year</option>
              <option value={moment().year()}>{moment().year()}</option>
              <option value={moment().year() + 1}>Next year</option>
            </select>
          </div>
        </div>
